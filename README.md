# AWS Aurora Cluster Snapshot Action


This Action allows you to create AWS Aurora Cluster Snapshot.

## Parameters
| Parameter | Type      | Default      | Description |
|-----------|-----------|--------------|-------------|
| `access_key_id` | `string`  |              | Your AWS access key id |
| `secret_access_key` | `string`  |              | Your AWS secret access key |
| `region` | `string`  |              | Your AWS region |
| `cluster_name` | `string`  |        | AWS Aurora Database Cluster Name |
| `prefix` | `string` | `backup`     | Prefix of the backup |

## Usage

```yaml
jobs:
  build-and-push:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    - uses: Durgaprasad-Budhwani/aws-aurora-cluster-snapshot@v1
      with:
        access_key_id: ${{ secrets.AWS_ACCESS_KEY_ID }}
        secret_access_key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
        region: ${{ secrets.REGION }}
        cluster_name: ${{ secrets.CLUSTER_NAME }}
        prefix: backup
```

If you don't want to use the latest docker image, you can point to any reference in the repo directly.

```yaml
  - uses: Durgaprasad-Budhwani/aws-aurora-cluster-snapshot@master
  # or
  - uses: Durgaprasad-Budhwani/aws-aurora-cluster-snapshot@v1
```

## License
The MIT License (MIT)