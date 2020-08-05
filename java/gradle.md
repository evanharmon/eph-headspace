# GRADLE

## Summary

Notes on using Gradle

## Properties File

gradle.properties

### Add Java path

`org.gradle.java.home={PATH TO JAVA}`

## Resources

## Wrapper Task

```
task wrapper(type: Wrapper) {
  gradleVersion = '2.11'
}
```

## Use Wrapper

`$ gradle wrapper`

## Build with Wrapper

`$ ./gradlew build`
