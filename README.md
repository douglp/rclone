# rclone using environment variables for authentication
## 1. In the remote configuration (in a file named rclone.conf, e.g.), set "env_auth = true", e.g. 
```
[linode]
type = s3
provider = Linode
env_auth = true
endpoint = us-iad-1.linodeobjects.com
```
## 2. For S3 buckets, use the following two environment variables 
```
# for access key
AWS_SECRET_ACCESS_KEY
# for secret key
AWS_SECRET_ACCESS_KEY
```
## 3. For sftp servers, use the environment variable `RCLONE_SFTP_KEY_FILE` and point to the local or mounted key file.

# Example command for rclone sync
```
rclone --config ./rclone.conf sync <source-remote>:<path> linode:<path>
```
