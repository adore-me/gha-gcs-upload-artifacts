# gha-gcs-upload-artifacts

## Description
Upload build artifacts to GCS.

## Inputs
| Key            | Required | Default | Description                                       |
|----------------|----------|---------|---------------------------------------------------|
| **gcs-sa**     | **true** | `N/A`   | Google service account to use for authenticating. |
| **gcs-bucket** | **true** | `N/A`   | Google Cloud Storage bucket name.                 |

## Outputs
**N/A**

## Notes
ℹ The path of the upload is preconfigured and it has the following structure:
```
BUCKET_NAME/REPO_NAME/PULL_REQUEST_NUMBER
```
**Ex:** `my-bucket/ms-tap/123`

### Example of step configuration and usage:
```yaml
steps:
  - name: 'Start Redis'
    uses: adore-me/gha-gcs-upload-artifacts@master
    with:
      gcs-sa: ${{ secrets.GCS_SA }}
      gcs-bucket: 'my-bucket'
```
