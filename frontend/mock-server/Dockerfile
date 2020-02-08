FROM node:13.8

USER node
ARG workdir="/home/node/mock-server"
ARG NODE_ENV=production
ENV NODE_ENV=${NODE_ENV}

RUN mkdir "$workdir"
WORKDIR "$workdir"

COPY . .
RUN set -ex &&\
 npm install &&\
 mkdir "$workdir/snapshots" &&\
 echo "Done!"

EXPOSE 3003
VOLUME ["$workdir", "$workdir/snapshots"]

CMD ["npm", "start"]
