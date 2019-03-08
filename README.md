# bwa-docker
Full Ubuntu 18.04 image with bwa installed

The image contains a full install of [bwa](https://github.com/lh3/bwa) (find the manual [here](http://bio-bwa.sourceforge.net/bwa.shtml)), including all necessary dependencies. I am not part of the bwa team - I just made this image.

In detail, the image is set up with:
 - Ubuntu 18.04
 - bwa 0.7.17-r1198-dirty (github commit 20d0a13092aa4cb73230492b05f9697d5ef0b88e, Jan 23 2019)

To run bwa you can do the following (this will mount the directory `/home/working` of the container to the current working directory on your local machine, and allow you to access files in this directory and any sub-directories):
```bash
$ docker run --rm -v $(pwd):/home/working -w /home/working chrishah/bwa bwa
```

You can also enter the container environment and work within it. All executables should be in the `PATH`.
```bash
$ docker run -it --rm -v $(pwd):/home/working -w /home/working chrishah/bwa /bin/bash
```

