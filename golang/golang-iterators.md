# GOLANG ITERATORS

## Summary

Notes on using golang iterators / loops

## Resources

[For](https://gobyexample.com/for)

## For Range

```golang
for _, e := range os.Environ() {
    pair := strings.Split(e, "=")
    fmt.Println(pair[0])
}
```

### Iterating Array Of Strings

must reference both return variables from `for ... range`. First variable
returned is of type int (index)

```golang
envs := []string{"GOOGLE_PROJECT_ID", "GOOGLE_APPLICATION_CREDENTIALS"}
for _, v := envs {

}
```

## Break Out Of For Loop

```golang
for {
		fmt.Println("loop")
		break
}
```

## Break But Continue For Loop

```golang
for n := 0; n <= 5; n++ {
	if n%2 == 0 {
		continue

	}
	fmt.Println(n)
}
```
