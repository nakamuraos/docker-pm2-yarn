FROM node:15-buster
LABEL maintainer="thinh.hoang <thinhhoang3030@gmail.com>"

# Install pm2, yarn
RUN npm install pm2 -g

# Expose ports needed to use Keymetrics.io
EXPOSE 80 443

# Start ecosystem-production.json process file
CMD ["pm2-runtime", "start", "ecosystem-production.json"]