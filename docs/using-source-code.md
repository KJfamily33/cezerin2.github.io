### Using Source code

### A) Cezerin Installtation
  
  - **Clone Git repositor**
  ```shell
  cd /var/www
  git clone https://github.com/cezerin2/cezerin2
  ```
  
  - **Change settings**
  ```shell
  cd /var/www/cezerin2/config
  ```
  
    Open `server.js` and change
  
      - MongoDB Creditionals
      - SMTP Settings
      - JWT and Cookie Secret Key
    
    Save file and go back to root app direcotry
    ```shell
    cd ../
    ```
  
  - **Install dependencies**
  ```shell
  npm i
  ```
  
  - **Setup database** Prepare database at this setup our database is empty. To add default data, indexes and access token we need to run:
  ```shell
  npm run setup <email> <domain>
  ```
  
    We don't have domain, so we'll use our local ip:
    ```shell
    npm run setup admin@example.com http://127.0.0.1
    ```
    This script will add token with email admin@example.com and my domain to http://127.0.0.1
    
  - **Start application**
  ```shell
  pm2 start process.json
  ```
  
    At this setup, we have api running on port 3001
