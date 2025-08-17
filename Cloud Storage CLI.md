#cli 

A compilation of [[Gcloud CLI]] commands to manage [[Cloud Storage]]
# Creation

- Create a new bucket
```sh
gcloud storage buckets create gs://${BUCKET_NAME}
```
- Create a new object within a bucket (upload file)
```sh
gcloud storage cp ${LOCAL_FILE_PATH} gs://${BUCKET_NAME}
```
- Retrieve a object from remote bucket (download file)
```sh
gcloud storage cp -r gs://${BUCKET_NAME}/${REMOTE_FILE_PATH} ${LOCAL_TARGET_FILE_PATH}
```
- Copy a remote object to a remote target file path (Copy to a new path within the bucket)
```sh
gcloud storage cp gs://${BUCKET_NAME}/${REMOTE_FILE_PATH} gs://${BUCKET_NAME}/${REMOTE_TARGET_FILE_PATH}
```

# Deletion

- Delete an object from a bucket
```sh
gcloud storage rm gs://${BUCKET_NAME}/${REMOTE_FILE_PATH}
```

# List

- List objects in a bucket
```sh
gcloud storage ls gs://${BUCKET_NAME}
```
- List objects in a bucket with details
```sh
gcloud storage ls -l gs://${BUCKET_NAME}/${REMOTE_FILE_PATH}
```


# Security

- Change [[Access Control List]] to make the object readable to AllUsers (make a object public)
```sh
gsutil acl ch -u AllUsers:R gs://${BUCKET-NAME}/${REMOTE_FILE_PATH}
```
- Change [[Access Control List]] to make the object not readable to AllUsers (make a object private)
```sh
gsutil acl ch -d AllUsers gs://${BUCKET-NAME}/${REMOTE_FILE_PATH}
```