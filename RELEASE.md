# Release checklist

* Make sure you have a GITHUB_TOKEN set.
  ```bash
  export GITHUB_TOKEN="..."
  ```
* Choose the next [release tag](https://github.com/earthly/earthly/releases).
  ```bash
  export RELEASE_TAG="v..."
  ```
* Run
  ```bash
  earth \
    --build-arg RELEASE_TAG \
    --secret GITHUB_TOKEN \
    --push -P +release
  ```
* Run
  ```bash
  earth \
    --build-arg RELEASE_TAG \
    --build-arg GIT_USERNAME=vladaionescu \
    --build-arg GIT_NAME="$(git config user.name)" \
    --build-arg GIT_EMAIL="$(git config user.email)" \
    --secret GITHUB_TOKEN \
    --push +release-homebrew
  ```
