# Instructions
Clone the repository and go in the directory.
`git submodule init`
`git submodule update`
Then change to desired version's directory and run:
`docker build -t <docker-hub-user>/<repo-name>:<tag> .`
And run the following to push into dockerhub.
`docker push <docker-hub-user>/<repo-name>:<tag>`
