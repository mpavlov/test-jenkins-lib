![](https://img.shields.io/badge/development%20status-obsoleted-red.svg)

## Obsoleted

Development on this library has been moved to https://github.com/spotify/jenkins-coverage-poster. The current repository will receive no further updates.

## Summary

A Jenkins 2.0 Pipeline library for automatically posting code coverage results to GitHub pull requests.

Currently supports:
 * input
   * jacoco html
 * output
   * github.com
   * github enterprise

## Example usage
In your Jenkinsfile:
```
@Library('github.com/mpavlov/test-jenkins-lib') _

stage("Run tests") {
  sh "mvn test"
}

stage("Post coverage") {
  postJacocoCoverage(threshold: 75)
}
```

## Example result

<img src="./coverage_pass.png" width="700" />

## Requirements

Your Jenkins must be version 2.0 or later and must define a Credential called `github-user-token`, which contains as password a valid GitHub api token. The Credential username can be anything, as it is not used. The token's permissions must allow read access to repositories and posting comments to pull requests at minimum.

