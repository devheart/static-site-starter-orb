# Static Site Starter Orb
> A CircleCI orb for the Static Site Starter project.

## Example usage
```yaml
version: 2.1

orbs:
  sss: devheart/static-site-starter@0.3

jobs:
  build_and_deploy:
    docker:
      - image: circleci/ruby:2.6.6-node
    environment:
      JEKYLL_ENV: production
      NOKOGIRI_USE_SYSTEM_LIBRARIES: true
    steps:
      - checkout
      - sss/install
      - sss/build
      - sss/firebase_deploy:
          project_id: $FIREBASE_PROJECT_ID
          token: $FIREBASE_TOKEN

workflows:
  version: 2
  build_and_deploy:
    jobs:
      - build_and_deploy
```
