# AWS AMPLIFY

## Summary

Notes on using aws amplify sdk's, cli, etc

## Resources

[React Router Amplify Auth](https://www.rockyourcode.com/custom-react-hook-use-aws-amplify-auth/)

## Get Environment After Git Clone

```console
amplify env add
```

asks if you want to add an existing, displays list of envs from `team-provider-info.json`
choose existing environment

now do:

```console
amplify env checkout `env_name` --restore
```

This step adds the necessary amplify files that are in the gitgnore and not stored in the repo
