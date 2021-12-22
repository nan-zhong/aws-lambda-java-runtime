# Purpose
* Use Dockerfile to build an image that has graavlvm and its native-image tool installed
* Upload the image's new version to rabbitsign/graalvm-native-image on Docker Hub

# Commands
* `docker build . -t rabbitsign/graalvm-native-image`
* `docker push rabbitsign/graalvm-native-image`