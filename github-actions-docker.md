# GITHUB ACTIONS DOCKER

## Summary

Notes on using docker with github actions

## Resources

[GH Help Docker Container Action](https://help.github.com/en/articles/creating-a-docker-container-action)

## Actions

`$HOME` is persisted across Actions

## Docker Login Syntax

[Latest Beta Docker Login Syntax](https://github.com/actions/docker/issues/28)

```yaml
- name: Sign-in to Docker
  uses: actions/docker/login@master
  env:
    DOCKER_USERNAME: ${{ secrets.GITHUB_DOCKER_USERNAME }}
    DOCKER_PASSWORD: ${{ secrets.GITHUB_DOCKER_PASSWORD }}
```
