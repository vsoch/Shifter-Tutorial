# Shifter In A Box

Shifter-in-a-box is intended to provide a functional installation of shifter that can be used for testing and experimentation of Shifter without installing it on a real system. You will need to expose port 27017 to your machine for the MongoDB to successfully work.

The install uses a Centos:7 base os.  The install steps can be seen in the Dockerfile.

# Usage

    docker run -it --rm --expose 27017 --privileged -v shifter:/data scanon/shifterbox

At the prompt, you can start the services.

    [root@xxxxx /]$ /src/start.sh

And test the services

    [root@xxxxx /]$ /src/test.sh

To run a shifter container, you need to become the testuser (auser).

    [root@xxxxx /]$ su - auser

    # Pull the image
    [auser@xxxx /]$ shifterimg pull busybox
    2018-02-22T17:03:03 Pulling Image: docker:busybox, status: READY

    # Run shell to interact
    [auser@xxxx /]$ shifter --image=busybox sh
    ~ $
    
    
# Docker4Mac Users

If you are using Docker4Mac then you will need to install the squashfs module.  There
is a separate Docker image for this.

    docker run -it --rm --privileged scanon/squashfs
