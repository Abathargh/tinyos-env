## tinyos-env

A couple of different pre-built environments for building tinyos programs, I mainly use(d) them for practical lessons where I had to interface with a Shimmer2r.
They are all available on my  [docker hub](https://hub.docker.com/r/abathargh/tinyos).

### Usage

If you use an image with a tag ending in **nocode**, you have to use a local copy of the tinyos git repo and mount it as a volume in the **/tinyos** container dir. 
It's very important that you run the container with the **--privileged** flag to make it have access to the serial interfaceof the host machine; you can also use the **--device** 
flag, specifying the serial interface identifying the device you're using.

For images without the **nocode** tag:

```bash
docker run --rm --privileged -it abathargh/tinyos:<tag> bash
```

For images with the **nocode** tag:

```bash
docker run --rm --privileged -it -v /path/to/tinyos:/tinyos abathargh/tinyos:<tag> bash
```

### License

These images are published under MPL2, TinyOS is originally released under a BSD license that you can find [here](https://github.com/tinyos/tinyos-main/blob/master/licenses/bsd.txt).
