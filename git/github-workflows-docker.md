# GITHUB WORKFLOWS DOCKER

## Summary

Notes on using docker with github workflows

## Resources

[GH Help Docker Container Action](https://help.github.com/en/articles/creating-a-docker-container-action)
[GH Docker Action Deprecated](https://github.community/t5/GitHub-Actions/Where-did-actions-bin-and-actions-docker-go/td-p/34608)

## Actions

`$HOME` is persisted across Actions

## Docker Format

Docker action is deprecated - format is changed to:

## Docker Login Syntax

[Latest Beta Docker Login Syntax](https://github.com/actions/docker/issues/28)

```yaml
- name: Sign-in to Docker
  uses: actions/docker/login@master
  env:
    DOCKER_USERNAME: ${{ secrets.GITHUB_DOCKER_USERNAME }}
    DOCKER_PASSWORD: ${{ secrets.GITHUB_DOCKER_PASSWORD }}
```
