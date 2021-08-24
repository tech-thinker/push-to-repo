# push-to-repo

**Push to another github repository**

It's useful if you want to push files created with GitHub Actions to another GitHub repository.

## Requirements

- **`destination-github-username`** - target username
- **`destination-repository-name`** - target repository
- **`target-branch`** - repository's branch name
- **`source-directory`** - the assets you want to push to
- **`user-name`** - committer name (Optional)
- **`user-email`** - committer email (Optional)

- **`API_TOKEN_GITHUB` (env) Personal Access Token (PAT)**

Generate your personal token following the steps:

- Go to the Github Settings (on the right hand side on the profile picture)
- On the left hand side pane click on "Developer Settings"
- Click on "Personal Access Tokens" (also available at https://github.com/settings/tokens)
- Generate a new token, choose "Repo". Copy the token.

Then make the token available to the Github Action following the steps:

- Go to the Github page for the repository that you push from, click on "Settings"
- On the left hand side pane click on "Secrets"
- Click on "Add a new secret" and name it "GIT_PAT_TOKEN"

## Usage

```yml
- name: Pushes to Repository
  uses: tech-thinker/push-to-repo@main
  env:
    API_TOKEN_GITHUB: ${{ secrets.GIT_PAT_TOKEN }}
  with:
    user-name: "github-actions[bot]"
    user-email: github-actions[bot]@users.noreply.github.com
    source-directory: "output-dir"
    destination-github-username: "username"
    destination-repository-name: "repo-name"
    target-branch: main
```

licensed under [MIT License](LICENSE)
