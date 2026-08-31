# composite-actions

Shared GitHub Actions for optyfr-org repositories.

## Actions

### setup-gradle

Sets up GraalVM JDK and Gradle.

| Input | Description | Default |
|---|---|---|
| `java-version` | Java version to use | `25` |
| `java-distribution` | Java distribution to use | `graalvm` |

### build-cache

Saves or restores the build cache keyed by SHA.

| Input | Description | Default |
|---|---|---|
| `mode` | `save` or `restore` | *required* |
| `cache-name` | Cache name prefix | `cache-builds` |
| `path` | Cache path(s) | `build` |

### upload-jacoco

Uploads JaCoCo coverage report as an artifact.

| Input | Description | Default |
|---|---|---|
| `path` | Path to the JaCoCo report directory | `build/reports/jacoco/` |
| `name` | Artifact name | `jacoco-coverage-report` |
| `retention-days` | Artifact retention period in days | `30` |

### ensure-release

Creates a GitHub release if it does not already exist.

| Input | Description | Default |
|---|---|---|
| `tag` | Release tag name | *required* |
| `repo` | GitHub repository (owner/repo) | `${{ github.repository }}` |
| `token` | GitHub token for authentication | *required* |

### upload-release-asset

Uploads a file to a GitHub release.

| Input | Description | Default |
|---|---|---|
| `tag` | Release tag name | *required* |
| `file` | Path to the file to upload | *required* |
| `repo` | GitHub repository (owner/repo) | `${{ github.repository }}` |
| `token` | GitHub token for authentication | *required* |

## Usage

```yaml
- uses: optyfr-org/composite-actions/setup-gradle@v1
```
