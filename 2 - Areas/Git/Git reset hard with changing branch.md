
I have a local feature branch: `my-feature-branch`, after development, I want to set the `staging` branch the same as my feature branch. Previously, I would have to change the branch and use `git reset --hard`:
```sh
git checkout my-feature-branch
# do development, commit and push
# after development

git checkout staging
git reset --hard my-feature-branch
git push -f
```

Switching branch may cause code compilation which I want to avoid.


```sh
git checkout my-feature-branch
# do development, commit and push
# after development

git fetch

git push --force-with-lease origin my-feature-branch:refs/heads/staging
# or this since you are at branch my-feature-branch
# git push --force-with-lease origin HEAD:refs/heads/staging

# This will not change your local staging branch
```

If you want to also update the local staging branch:
```sh
git branch -f staging my-feature-branch
```