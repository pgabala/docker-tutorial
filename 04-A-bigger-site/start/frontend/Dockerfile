FROM node:alpine
WORKDIR /app
COPY . /app
RUN npm install
ENV NODE_ENV production
ENV PORT 3000
CMD ["npm", "start"]


# TODO: add the Docker commands to do these steps:

# at build time:
# set the current directory
# copy the manifest file: package.json
# `npm install`
# copy the content into place
# let traffic flow in on port 3000

# as the container starts:
# `npm start`
