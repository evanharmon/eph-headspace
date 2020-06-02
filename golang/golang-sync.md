# GOLANG SYNC

## Summary

Notes on using the golang sync package including wait groups

## Resources

[Wait Group Tutorial](https://tutorialedge.net/golang/go-waitgroup-tutorial/)

## Wait Group For Loop

```golang
func run(ctx context.Context, svc *sqs.Client, h Handler, messages []sqs.Message) {
	numMessages := len(messages)

	var wg sync.WaitGroup
	wg.Add(numMessages)
	for i := range messages {
		go func(m sqs.Message) {
			defer wg.Done()
			if err := handleMessage(ctx, svc, m, h); err != nil {
				Log.Error(err.Error())
			}
		}(messages[i])
	}
}
```
