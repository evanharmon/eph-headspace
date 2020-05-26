# LOCAL FIRST APPROACH

## Summary

notes on local first applications

## Resources

- [Local First WhitePaper](https://martin.kleppmann.com/papers/local-first.pdf)
- [AutoMerge Github Repo](https://github.com/automerge/automerge)
- [WebRTC framework](https://webrtc.org/)

### Local First Whitepaper

local copy of your data is the primary copy

- functional reactive programming (like React) works well with CRDTs via a
  single reducer

#### Seven Ideals

##### No spinners

##### Work is not trapped on a device

##### Network is optional

##### Seamless collaboration with others

##### The long now (should be able to work forever)

- use common formats such as JSON or SQLite

##### Security and privacy by default

- use end to end encryption

##### User retains ultimate ownership and control

##### Existing data and storing models

#### Sharing

URLs are a good mechanism

#### Cloud Compute / Cloud Peers Benefits

- burst computing
- archival / backup
- bridge to traditional APIs
