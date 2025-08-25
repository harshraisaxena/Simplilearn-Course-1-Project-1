#!/bin/bash

# === Jenkins Backup Script ===
# This will compress Jenkins home directory and upload to S3

# Variables
JENKINS_HOME="/var/lib/jenkins"
S3_BUCKET="simplilearn-course2-project1"
TIMESTAMP=$(date +%F_%H-%M-%S)
BACKUP_FILE="/tmp/jenkins_backup_$TIMESTAMP.tar.gz"

# Create backup
tar -czf $BACKUP_FILE $JENKINS_HOME

# Upload to S3
aws s3 cp $BACKUP_FILE s3://$S3_BUCKET/

# Remove local backup
rm -f $BACKUP_FILE

echo "Backup completed and uploaded to s3://$S3_BUCKET/"
