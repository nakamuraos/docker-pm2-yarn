FROM thinhhv/pm2:latest

# Bundle APP files
COPY package.json .
COPY ecosystem-production.json .

# Install app dependencies
RUN yarn install --production \
  && yarn cache clean \
  && node-prune

# Copy source
COPY src src/

# Show current folder structure in logs
RUN ls -al -R

EXPOSE 3000

CMD [ "pm2-runtime", "start", "ecosystem-production.json" ]