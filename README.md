# MkDocs Docker image for GitLab CI

A Docker image for MkDocs and MkPDFs projects.

## Usage

As the Docker image is automatically build on Docker Hub, you can use it straight in your pipeline:

```yaml
image: marcandreappel/docker-mkdocs-gitlab-ci:latest

test:
  stage: test
  script:
    - mkdocs build --strict --verbose --site-dir test
  artifacts:
    paths:
      - test
  except:
    - master

pages:
  stage: deploy
  script:
    - mkdocs build --strict --verbose
  artifacts:
    paths:
      - public
  only:
    - master
...
```
