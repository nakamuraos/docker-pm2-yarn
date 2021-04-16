# Docker layer PM2 + YARN

## How to use:
- Dockerfile example:
  ```bash
  # Dockerfile
  # ----------

  FROM thinhhv/pm2:latest

  # Bundle APP files
  COPY src src/
  COPY package.json .
  COPY ecosystem-production.json .

  # Install app dependencies
  ENV NPM_CONFIG_LOGLEVEL warn
  RUN yarn install --production

  # Show current folder structure in logs
  RUN ls -al -R

  CMD [ "pm2-runtime", "start", "ecosystem-production.json" ]
  ```

## How to build:
  ```bash
  docker build -t thinhhv/pm2:latest .
  ```
