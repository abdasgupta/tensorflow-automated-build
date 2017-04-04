# Automated build of TensorFlow binary using a Docker image

## Build the image

```bash
$ git clone https://github.com/ai-infra/tensorflow-automated-build.git
$ cd tensorflow-automated-build
$ docker build -t ppc64le/tensorflow-bin -f Dockerfile.ppc64le .
```

## Copy the Tensorflow and Bazel binaries to local folder on the host

Assume /foo is a folder on the host


```bash
$ docker run -v /foo:/foo ppc64le/tensorflow-bin /bin/bash -c "cp -R /output/*.whl /foo"
```

```bash
$ docker run -v /foo:/foo ppc64le/tensorflow-bin /bin/bash -c "cp -R /usr/bin/bazel /foo"
```
