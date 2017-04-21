![](https://img.shields.io/badge/development%20status-alpha-yellow.svg) [![Apache 2.0](https://img.shields.io/badge/license-Apache%20License%202.0-blue.svg)](http://www.apache.org/licenses/LICENSE-2.0)

A Jenkins 2.0 Pipeline library for automatically posting code coverage results to GitHub pull requests.

Currently supports:
 * input
   * jacoco html
 * output
   * github.com
   * github enterprise

## Example usage
Adding this to your Jenkinsfile:
```
@Library('github.com/mpavlov/test-jenkins-lib') _

stage("Post coverage") {
  postJacocoCoverage(threshold: 75)
}
```

... gives you this in your Pull Request:

<img src="./coverage_pass.png" width="700" />

### Requirements

Your Jenkins must be version 2.0 or later and must define a Credential called `github-user-token`, which contains as password a valid GitHub api token. The Credential username can be anything, as it is not used. The token's permissions must allow read access to repositories and posting comments to pull requests at minimum.

## Code of conduct
This project adheres to the [Open Code of Conduct][code-of-conduct]. By participating, you are expected to honor this code.

[code-of-conduct]: https://github.com/spotify/code-of-conduct/blob/master/code-of-conduct.md
