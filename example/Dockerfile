# https://developers.home-assistant.io/docs/add-ons/configuration#add-on-dockerfile
ARG BUILD_FROM
FROM $BUILD_FROM

# Execute during the build of the image
ARG TEMPIO_VERSION BUILD_ARCH
RUN \
  apk add --no-cache \
    python3 py3-pip py3-wheel
RUN pip install --upgrade pip
RUN pip install --prefer-binary pyess

