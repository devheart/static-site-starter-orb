# Static Site Starter Orb
> A CircleCI orb for the Static Site Starter project.

## Example usage
```yaml
version: 2.1

orbs:
  sss: devheart/static-site-starter@0.3

workflows:
  version: 2
  build_and_deploy:
    jobs:
      - sss/build_and_deploy
```
