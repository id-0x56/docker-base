FROM alpine:latest

ARG USERNAME=user
ARG USER_UID=1000
ARG USER_GID=$USER_UID

RUN addgroup --system --gid $USER_GID $USERNAME \
    && adduser --system --uid $USER_UID --ingroup $USERNAME $USERNAME

ENV TZ=Europe/London
RUN apk add --no-cache tzdata \
    && ln -snf /usr/share/zoneinfo/$TZ /etc/localtime \
    && echo $TZ > /etc/timezone

# ENV TZ=Europe/London
# RUN apk add --no-cache alpine-conf \
#     && setup-timezone -z $TZ

USER $USERNAME



# docker builder prune -af \
#     && docker system prune -af \
#     && docker volume prune -f \
#     && docker image prune -af

# docker login
# docker build --no-cache -t 00x56/docker-alpine:latest alpine
# docker push 00x56/docker-alpine:latest

# docker run --rm --interactive --tty 00x56/docker-alpine /bin/sh
# docker exec --interactive --tty --user root 7809913082a3 /bin/sh
# docker exec --interactive --tty 7809913082a3 /bin/sh
