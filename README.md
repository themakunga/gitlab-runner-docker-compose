# GitLab Runner with Docker Compose

Compose configuration for GitLab Runner using the official
`gitlab/gitlab-runner:alpine` image.

## Requirements

- Docker with the Compose plugin.
- Access to the GitLab instance where the runner will be registered.
- The runner registration values required by [`docker-compose.yml`](docker-compose.yml).

## Configuration

Copy the supplied example and edit the local values:

```sh
cp .env.example .env
```

The Compose file references `GITLAB_URL`, `GITLAB_REGISTRATION_TOKEN`, `RUNNER_NAME`
and `USERDIR`. Keep the registration token private and review the volume mappings
before starting the services.

```sh
docker compose config --quiet
docker compose up -d
docker compose ps
docker compose logs --tail=100
```

The GitLab instance must support the registration mechanism configured in this
Compose file. Review the upstream runner requirements before upgrading the image.
See [LICENSE](LICENSE) for license terms.
