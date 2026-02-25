## Useful Commands

```bash
# Run initial setup (only once)
bash scripts/setup-n8n.sh

# Start the n8n services
bash scripts/start-n8n.sh

# Stop all running n8n services
bash scripts/stop-n8n.sh

# Create a backup of your n8n instance
bash scripts/backup-n8n.sh

# Restore n8n from a backup file
bash scripts/restore-n8n.sh

# Update n8n to the latest version
bash scripts/update-n8n.sh
```

## Backup File Transfer with SFTP

After creating a backup with `bash scripts/backup-n8n.sh`, you can easily download it from your server to your local machine using **SFTP**.

```bash
# first disconnect from your SSH session
exit

# now start an SFTP session from your local machine
sftp ubuntu@<your-server-public-ip>

# navigate to the backups folder on the server
cd n8n-compose/backups

# list files sorted by time (newest first)
ls -t

# download the latest backup file
get n8n_backup_00000000_000000.tar.gz

# disconnect from the SFTP session
exit
```

This will copy the selected backup file into your current local directory.  
You can also use `get -r backups` to download the entire backups folder at once.
