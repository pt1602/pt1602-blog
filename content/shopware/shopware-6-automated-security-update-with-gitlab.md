---
title: "Shopware 6 automated security update with Gitlab"
date: 2022-08-25T10:19:31+02:00
draft: false
---

This pipeline automatically creates a Merge Request with an update of the Shopware Security Plugin, based on a tag.

## Requirements

* Gitlab 
* Shopware 6 composer setup

### Variables

* SSH_DEPLOY_PRIVATE_KEY
  * Private Key of a created key pair needs to be stored in this variable
  * Public Key needs to be entered under "Settings > Repository > Deploy Key"
    * Do not forget to grant write permissions
* SSH_KNOWN_HOSTS 
  * Get those from the [Gitlab Documentation](https://docs.gitlab.com/ee/user/gitlab_com/#ssh-known_hosts-entries)

## Code

```
stages:
  - security

securityUpdate:
  stage: security
  rules:
    - if: '$CI_COMMIT_TAG =~ /security-.*/'
  image: "kellerkinder/pipeline-image:8.0"
  before_script:
    - eval $(ssh-agent -s)
    - echo "${SSH_DEPLOY_PRIVATE_KEY}" | tr -d '\r' | ssh-add -
    - mkdir -p ~/.ssh && > ~/.ssh/known_hosts
    - echo "$SSH_KNOWN_HOSTS" >> ~/.ssh/known_hosts
    - chmod 700 ~/.ssh
    - git config user.name "security"
    - git config user.email "ci@example"
    - git remote remove origin || true
    - git remote add origin "git@gitlab.com:path/repo.git"
  script:
    - cd ${CI_PROJECT_DIR} && composer install --no-interaction --optimize-autoloader
    - composer update store.shopware.com/swagplatformsecurity
    - git checkout -b feature/security-patch-$(date +%F)
    - git add -A
    - git commit -m "Security Update $(date +%F)" || echo "No changes to commit"
    - git push --set-upstream origin feature/security-patch-$(date +%F)
```

## Tag Example

`security-YYMMDD`

