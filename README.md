# Supported tags and respective `Dockerfile` links

- [`1.0.1` (*1.0.1/Dockerfile*)](https://github.com/di/vintage-python/blob/master/1.0.1/Dockerfile)
- [`1.3` (*1.3/Dockerfile*)](https://github.com/di/vintage-python/blob/master/1.3/Dockerfile)

# What is this?

The official [Python Releases](https://www.python.org/downloads/) page lists recent downloads all the way back to 2.0.1, from June 22nd, 2001.

But wait, there's more! Also available are [various source
releases](https://legacy.python.org/download/releases/src/) for versions that
go back even farther, back to Python 1.0.1, released Feb 15th, 1994.

These base images make it easier to run the more "vintage" Python versions, directly from the comfort of your modern environment.

# Why would I want this?

For fun, for history's sake, for archaeology, for science! Or maybe you want to containerize that ancient 1.x project you're still running in production (not recommended).

# How to use this image

## Create a `Dockerfile` in your Python app project

```
FROM dustingram/vintage-python:1.0.1

WORKDIR /tmp

RUN echo "import sys; print 'Python: ' + sys.version" > main.py

CMD ["python", "./main.py"]
```

You can then build and run the Docker image:

```
$ docker build -t my-vintage-python-app .
Sending build context to Docker daemon  2.048kB
...
Successfully tagged my-vintage-python-app:latest

$ docker run -it --rm my-vintage-python-app
Python: 1.0.1 (Feb 23 2019)
```

(The date here is when the image was built, not when the source was published)
