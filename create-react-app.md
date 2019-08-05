# CREATE REACT APP

## Summary

Notes on working with the `create-react-app` npm package

## Resources

[Github](https://github.com/facebook/create-react-app)
[Docs](https://facebook.github.io/create-react-app/)

## Implement Create React App On Existing Repo

Major Pain In The Ass (PITA)

1. Create New Folder Locally

```console
npx create-react-app my-app-folder-name
cd my-app-folder-name
```

2. Add Origin Of Existing Repo

```console
git remote add origin https://github.com/evanharmon/my-repo.git
```

3. Pull Old Master From Origin To Backup Local Branch

This is to make old repo src code / files easier to copy over to new repo

```console
git checkout -b backup/non-cra-master
git reset --hard origin/master
```

4. Rebase Init Create React App Commit On To Master

Need to get in to a git state where you can starting migrating backup/non-cra-master to
feature/cra-scaffold. This may obliterate some changes from backup/non-cra-master that
you'll have to re-introduce.

```console
git checkout master
git checkout -b feature/cra-scaffold
git rebase -Xtheirs backup/non-cra-master
```

5. Copy Assets / Code As Needed

Let's say you want to grab the image assets from the fork and use them in
your react app. Assume the assets are located at `public/assets` in the original
repo and you want them located at `src/assets` in the react app.

\*\*Note: You can't checkout a folder to a new folder path. Has to be done in
separate steps

```console
git checkout backup/non-cra-master public/assets
git mv public/ src/
```
