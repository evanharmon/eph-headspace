# RUST WAVS

## Summary
Notes on readiung and writing WAV files in Rust

## Read 16bit Mono Samples And Convert To Float 32
```rust
extern crate hound;
extern crate sample;

use hound::WavReader;
use sample::{signal, Sample, Signal};

fn print_samples_f32(filename: &str) {
    let mut reader = WavReader::open(filename).unwrap();
    let samples: Vec<f32> = reader
        .samples()
        .filter_map(Result::ok)
        .map(i16::to_sample::<f32>)
        .collect();
    for _sample in samples {
        if _sample > 0.5 {
            println!("Sample: {}", _sample);
        }
    }
}

fn main() {
    let file16bit = "assets/my-sound.wav";
    print_samples_f32(file16bit);
}
```

## Read 24bit Mono Samples And Convert To Float 32
```rust
extern crate hound;
extern crate sample;

use hound::WavReader;
use sample::{signal, Sample, Signal};

fn convert_wav_pcm_24bit_to_f32() {
    let mut wav_reader = WavReader::open("assets/gold_24bit_44100_SD_XD5_001_Clean.wav").unwrap();

    assert_eq!(wav_reader.spec().channels, 1);
    assert_eq!(wav_reader.spec().sample_rate, 44_100);
    assert_eq!(wav_reader.spec().bits_per_sample, 24);
    assert_eq!(wav_reader.spec().sample_format, SampleFormat::Int);

    let samples: Vec<f32> = wav_reader
        .samples()
        .map(|s| s.unwrap())
        .map(|s| Sample::to_sample::<f32>(I24::new(s).unwrap()))
        .collect();

    // The test file has been prepared with these exact samples
    assert_eq!(
        &samples[0..8],
        &[
            0.0,
            -0.14937639,
            -0.0061297417,
            -0.07352567,
            -0.25857913,
            -0.07417166,
            0.08680165,
            -0.00491035,
        ]
    );
}
```

## Example Test read 24bit WAV
[Rust](https://github.com/ruuda/hound/blob/master/src/read.rs#L1150)
```rust
extern crate hound;
extern crate sample;

use hound::WavReader;
use sample::{signal, Sample, Signal};

fn read_wav_wave_format_extensible_pcm_24bit() {
    let mut wav_reader = WavReader::open("testsamples/waveformatextensible-24bit-192kHz-mono.wav")
        .unwrap();

    assert_eq!(wav_reader.spec().channels, 1);
    assert_eq!(wav_reader.spec().sample_rate, 192_000);
    assert_eq!(wav_reader.spec().bits_per_sample, 24);
    assert_eq!(wav_reader.spec().sample_format, SampleFormat::Int);

    let samples: Vec<i32> = wav_reader.samples()
                                      .map(|r| r.unwrap())
                                      .collect();

    // The test file has been prepared with these exact four samples.
    assert_eq!(&samples[..], &[-17, 4_194_319, -6_291_437, 8_355_817]);
}
```

## Create Stereo Signal From Mono WAV
```rust
    let filename = "assets/user_single_clap.wav";
    let reader = WavReader::open(filename).unwrap();
    let i32_samples: Vec<i32> = reader.into_samples().map(|s| s.unwrap()).collect();
    let i24_samples: Vec<I24> = i32_samples
        .into_iter()
        .map(|s| I24::new(s).unwrap())
        .collect();
    let f32_samples: Vec<f32> = i24_samples.into_iter().map(I24::to_sample::<f32>).collect();
    let frames: Vec<_> = f32_samples.into_iter().map(|s| [s, s]).collect();
    let signal = signal::from_iter(frames.iter().cloned());
```

## Convert 24bit Stereo WAV To Signal
Allows access to interleaved sample amplitudes as a frame
```rust
fn main() {
    let filename = "assets/user_single_clap.wav";
    let reader = WavReader::open(filename).unwrap();
    let i32_samples: Vec<i32> = reader
        .into_samples()
        .map(|s| s.unwrap())
        .collect::<Vec<i32>>();
    let i24_samples: Vec<I24> = i32_samples
        .into_iter()
        .map(|s| I24::new(s).unwrap())
        .collect();
    let f32_samples = i24_samples
        .into_iter()
        .map(I24::to_sample::<f32>)
        .collect::<Vec<f32>>();
    let signal = signal::from_interleaved_samples_iter::<_, [f32; 2]>(f32_samples.into_iter());
    for _frame in signal.until_exhausted() {
        println!("{:?}", _frame);
    }
}
```
