# Exoscale CLI

### Create IAM Access Key with access to SOS Bucket

    exo iam access-key create access_key_my_bucket_name_bucket --operation "get-sos-object" --operation "list-sos-bucket" --operation "put-sos-object" --operation "delete-sos-object" --operation "abort-sos-multipart-upload" --operation "list-sos-bucket-multipart-uploads" --resource sos/bucket:my_bucket_name
