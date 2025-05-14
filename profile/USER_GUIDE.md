## Deployment

# 1. Set up an Apache server
   
# 2. Clone the repository’s /src/ (source) directory into the Apache server’s main directory.
- If you want it elsewhere, you may need to configure the .htaccess file within the /src/ directory and the BASE_URL option within the /src/.env file.

# 3. Set up the MySQL database
- You can either configure src/.env to your liking or tailor your MySQL database to match the default configuration of /src/.env
- If you wish to use another database type, you can configure the /src/.env to match what you want. Relevant configuration options are:
  DB_ENGINE
  DB_HOST
  DB_PORT
  DB_DB
  DB_USERNAME
  DB_PASSWORD
  DB_CONNECTION_STR
- If the desired database does not exist, you must manually create it.

# 4. Migrate database
- Navigate to /ilgar/migrate on the web server, and you will get a message saying migrations were successful.

## Storage
Files are stored within the INTERNAL_STORAGE_DIR directory configured in /src/.env. If this directory does not exist, you must create it before files can be successfully uploaded and saved.

Uploaded files will be placed within directories corresponding to the uploading user’s unique user identifier (i.e., INTERNAL_STORAGE_DIR/4). Directories the user creates will also reside within this folder. The file name of an uploaded file will be the SHA-256 hash of the file’s contents with the original file extension (i.e., INTERNAL_STORAGE_DIR/4/c4d33…55e.txt).
