# MkDocs Docker image for GitLab CI

A Docker image for MkDocs projects, including the `with-pdf` plugin.

![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/marcandreappel/docker-mkdocs-gitlab-ci?logo=docker&style=for-the-badge)
![Docker Image Size (latest by date)](https://img.shields.io/docker/image-size/marcandreappel/docker-mkdocs-gitlab-ci?logo=ubuntu&sort=date&style=for-the-badge)

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
