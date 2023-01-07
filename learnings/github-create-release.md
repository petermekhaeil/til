# Create a release in GitHub using API

There are 3 ways to create a release using the GitHub API. 

## Parameters

- `tag_name`: The name of the tag.
- `name`: The name of the release.
- `body`: The description of the release.

There are more parameters in the [documentation](https://docs.github.com/en/rest/releases/releases#create-a-release).

Sample repository with releases: [git-tag-release](https://github.com/petermekhaeil/git-tag-release/releases).

## Using cURL

```bash
curl \
  -X POST \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <YOUR-TOKEN>"\
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/repos/OWNER/REPO/releases \
  -d '{"tag_name":"v0.0.0","name":"v0.0.0","body":"Full Changelog: https://github.com/OWNER/REPO/commits/v0.0.0"}'
```

## Using JavaScript

Using [Octokit](https://github.com/octokit/core.js#readme):

```js
const octokit = new Octokit({
  auth: 'YOUR-TOKEN'
});

await octokit.request('POST /repos/{owner}/{repo}/releases', {
  owner: 'OWNER',
  repo: 'REPO',
  tag_name: 'v0.0.0',
  name: 'v0.0.0',
  body: 'Full Changelog: https://github.com/OWNER/REPO/commits/v0.0.0'
});
```

## Using GitHub CLI

[GitHub CLI Manual](https://cli.github.com/manual/gh_api)

```bash
gh api \
  --method POST \
  -H "Accept: application/vnd.github+json" \
  /repos/OWNER/REPO/releases \
  -f tag_name='v0.0.0' \
  -f name='v0.0.0' \
  -f body='Full Changelog: https://github.com/OWNER/REPO/commits/v0.0.0'
```
