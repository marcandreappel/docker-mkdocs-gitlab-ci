# MkDocs Docker image for GitLab CI

A Docker image for MkDocs projects, including the `with-pdf` plugin.

## Usage

As the Docker image is automatically build on Docker Hub, you can use it straight in your pipeline:

```yaml
image: marcandreappel/docker-mkdocs-gitlab-ci:latest

test:
  stage: test
  script:
    - mkdocs build -c -s -v -d test
  artifacts:
    paths:
      - test
  # Optional
  except:
    - master

pages:
  stage: deploy
  script:
    - mkdocs build -s
  artifacts:
    paths:
      - public
  only:
    - master
...
```
