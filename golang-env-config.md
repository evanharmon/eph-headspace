# GOLANG ENV CONFIG

## Summary

Notes on using configs and envs in golang binaries

## Resources

[Config Package And Dotenv](https://dev.to/craicoverflow/a-no-nonsense-guide-to-environment-variables-in-go-a2f)

## Load .env

```golang
import "github.com/joho/godotenv"

if err := godotenv.Load(); err != nil {
   log.Printf("no .env file found, falling back to environment variables")
}
```

## Set Env Vars In Tests

pre-create a `env.example` with the named environment variables
