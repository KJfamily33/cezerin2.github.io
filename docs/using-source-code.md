### Using Source code

### A) Cezerin Backend (API) Installation
  
  - **Clone Git repository**
  ```shell
  cd /home/work/cezerin
  git clone https://github.com/cezerin2/cezerin2
  cd cezerin2
  ```
  
  - **Change settings**
  ```shell
  cd config
  ```
  - **Open `server.js` and change
  
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
  
    We don't have domain, so we'll use our local domain:
    ```shell
    npm run setup admin@example.com http://localhost
    ```
    This script will add token with email admin@example.com and my domain to http://localhost
    
  - **Start application in the background**
  ```shell
  pm2 start process.json
  ```

  - **or you can start app in your terminal (you will see debug information, that is useful for debug):  
  
  ```shell
  npm start
  ```
  
  - **At this setup, we have api running on port 3001 and available at http://localhost:3001
  
  - ** For example, here is the default store settings: http://localhost:3001/api/v1/settings  
  
  ```    
vam@vam:/home/work/cezerin/cezerin2$ npm start

> cezerin2@0.33.0 start /home/work/cezerin/cezerin2
> node -r esm src/index.js

info: API running at http://localhost:3001
info: MongoDB connected successfully
  ```

### B) Cezerin Frontend (Store) Installation

  - **Clone Git repository**
  ```shell
  cd /home/work/cezerin
  git clone https://github.com/cezerin2/cezerin2-store
  ```
  
  - **Change settings**
  ```shell
  cd cezerin2-store/config
  ```
  
    Open `store.js` and change
    
      - JWT and Cookie Secret Key
      
    Save file and go back to roop app direcotry
    ```shell
    cd ../
    ```
    
  - **Install dependencies**
  ```shell
  npm i
  ```
  
  - **Build project**
  ```shell
  npm run build
  ```
  
  - **Start cezerin store frontend application in the background**
  ```shell
  pm2 start process.json
  ```

    or you can start app in your terminal (you will see debug information, that is useful for debug):  
  
  ```shell
  npm start
  ```
  
    At this setup your cezerin store is now connected to api and available in browser at http://localhost:3000 
  
  ```    
> cezerin2-store@0.33.0 start /home/work/cezerin/cezerin2-store
> node -r esm dist/server/index.js

info: Store running at http://localhost:3000
  ```
    
    
### C) Cezerin Frontend (Admin Dashboard) Installation

  - **Clone Git repository**
  ```shell
  cd /home/work/cezerin
  git clone https://github.com/cezerin2/cezerin2-admin
  ```
  
  - **Change settings**
  ```shell
  cd /cezerin2-admin/config
  ```
  
    Open `admin.js` and change
    
      - api url
      - websocket url
      
    Save file and go back to roop app direcotry
    ```shell
    cd ../
    ```
    
  - **Install dependencies**
  ```shell
  npm i
  ```
  
  - **Build project**
  ```shell
  npm run build
  ```
  
  - **Start cezerin store frontend application in the background**
  ```shell
  pm2 start process.json
  ```
    or:  
  
  ```shell
  pm2 serve ./dist 3002
  ```
  
    At this setup your cezerin admin dashboard app is now connected to api and available in browser at http://localhost:3002 
  
  ```    
vam@vam:/home/work/cezerin/cezerin2-admin$ pm2 serve ./dist 3002
[PM2] Starting /usr/local/lib/node_modules/pm2/lib/API/Serve.js in fork_mode (1 instance)
[PM2] Done.
[PM2] Serving /home/work/cezerin/cezerin2-admin/dist on port 3002
┌─────────────────────────┬────┬───────┬────────┬────────┬─────┬────────┬───────────┐
│ Name                    │ id │ mode  │ status │ ↺      │ cpu │ memory │
├─────────────────────────┼────┼───────┼────────┼────────┼─────┼────────┼───────────┤
│ static-page-server-3002 │ 0  │ 3.2.9 │ fork   │ online │ 0   │ 0%     │ 29.3 MB   │
└─────────────────────────┴────┴───────┴────────┴────────┴─────┴────────┴───────────┘
 Use `pm2 show <id|name>` to get more details about an app

  ```
