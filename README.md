# GCPIGI
from google.cloud import storage

def upload_image_to_gcs(bucket_name, local_file_path, destination_blob_name):
    # Instantiate a client
    client = storage.Client()

    # Get the bucket
    bucket = client.get_bucket(bucket_name)

    # Create a new blob and upload the file
    blob = bucket.blob(destination_blob_name)
    blob.upload_from_filename(local_file_path)

    print(f"Image uploaded to Cloud Storage. Bucket: {bucket_name}, Blob: {destination_blob_name}")

# Usage
bucket_name = "your-bucket-name"
local_file_path = "path/to/local/image.jpg"
destination_blob_name = "uploaded-image.jpg"

upload_image_to_gcs(bucket_name, local_file_path, destination_blob_name)
pip install google-cloud-storage
