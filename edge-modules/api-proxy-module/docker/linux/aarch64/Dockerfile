#-------------------------------------------------------------------------------------------------------------
# Copyright (c) Microsoft Corporation. All rights reserved.
# Licensed under the MIT License. See https://go.microsoft.com/fwlink/?linkid=2090316 for license information.
#-------------------------------------------------------------------------------------------------------------

ARG DIR=.

FROM arm64v8/alpine:3.12.0
WORKDIR /app
COPY target/aarch64-unknown-linux-gnu/release/api-proxy-module .
COPY templates .
RUN	apk update && \
    apk add nginx && \
	mkdir /run/nginx
EXPOSE 443/tcp	
EXPOSE 80/tcp
EXPOSE 5000/tcp
EXPOSE 11002/tcp
EXPOSE 7000-8000/tcp
ENTRYPOINT ["/app/api-proxy-module"]
 