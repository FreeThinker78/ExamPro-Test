EXPORT GH_USERNAME='freethinker78'
export GH_TOKEN=''
export GH_IMAGE_NAME='hello-world'
export GH_VER='1.0.0'

env | grep GH_
GH_TOKEN=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
GH_IMAGE_NAME=hello-world
GH_USERNAME=FreeThinker78
GH_VER=1.0.0


echo $GH_TOKEN | docker login ghcr.io -u $GH_USERNAME --password-stdin

WARNING! Your password will be stored unencrypted in /home/codespace/.docker/config.json.
Configure a credential helper to remove this warning. See
https://docs.docker.com/engine/reference/commandline/login/#credentials-store

Login Succeeded

docker tag $IMAGE_NAME:$GH_VER ghcr.io/$GH_USERNAME/$IMAGE_NAME:$GH_VER

Error parsing reference: "ghcr.io/FreeThinker78/hello-world:1.0.0" is not a valid repository/tag: invalid reference format: repository name (FreeThinker78/hello-world) must be lowercase

docker images
REPOSITORY    TAG       IMAGE ID       CREATED          SIZE
hello-world   latest    6fa7e980050d   12 minutes ago   5.61MB
alpine        3.14      9e179bacf43c   14 months ago    5.61MB

docker tag $IMAGE_NAME:latest ghcr.io/$GH_USERNAME/$IMAGE_NAME:$GH_VER

docker push ghcr.io/$GH_USERNAME/$GH_IMAGE_NAME:$GH_VER

The push refers to repository [ghcr.io/freethinker78/hello-world]
9733ccc39513: Pushed 
1.0.0: digest: sha256:0795a7f21db81d82b8da0d847f058b8cb4a1759a8fe924eedd8dfa57b2b77af1 size: 528


LABEL org.opencontainers.image.source https://github.com/OWNER/REPO