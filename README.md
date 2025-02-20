# Supported tags and respective `Dockerfile` links

- [`0.9.1` (*0.9.1/Dockerfile*)](https://github.com/di/vintage-python/blob/master/0.9.1/Dockerfile)
- [`1.0.1` (*1.0.1/Dockerfile*)](https://github.com/di/vintage-python/blob/master/1.0.1/Dockerfile)
- [`1.1` (*1.1/Dockerfile*)](https://github.com/di/vintage-python/blob/master/1.1/Dockerfile)
- [`1.2` (*1.2/Dockerfile*)](https://github.com/di/vintage-python/blob/master/1.2/Dockerfile)
- [`1.3` (*1.3/Dockerfile*)](https://github.com/di/vintage-python/blob/master/1.3/Dockerfile)

# What is this?

The official [Python Releases](https://www.python.org/downloads/) page lists recent downloads all the way back to 2.0.1, from June 22nd, 2001.

But wait, there's more! Also available are [various source
releases](https://legacy.python.org/download/releases/src/) for versions that
go back even farther, back to Python 1.0.1, released Feb 15th, 1994.
Additionally, 0.9.1 has been provided here: https://github.com/smontanaro/python-0.9.1

These base images make it easier to run the more "vintage" Python versions, directly from the comfort of your modern environment.

# Why would I want this?

For fun, for history's sake, for archaeology, for science! Or maybe you want to containerize that ancient 1.x project you're still running in production (not recommended).

# How to use this image

## Run a vintage Python REPL

```
$ docker run -it dustingram/vintage-python:1.0.1
Python 1.0.1 (Feb 23 2019)
Copyright 1991-1994 Stichting Mathematisch Centrum, Amsterdam
>>> print "Hello world!"
Hello world!
>>>
```

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

## Timeline of 'vintage' Python releases
From https://python-history.blogspot.com/2009/01/brief-timeline-of-python.html

Release Date      | Version | Notes
------------------|---------|------------------------
December, 1989    |         | Implementation started
1990              |         | Internal releases at CWI
February 20, 1991 | 0.9.0   | (released to alt.sources)
February, 1991    | [0.9.1](https://github.com/di/vintage-python/tree/master/0.9.1) |
Autumn, 1991      | 0.9.2   |
December 24, 1991 | 0.9.4   |
January 2, 1992   | 0.9.5   | (Macintosh only)
April 6, 1992     | 0.9.6   |
Unknown, 1992     | 0.9.7beta |
January 9, 1993   | 0.9.8   |
July 29, 1993     | 0.9.9   |
January 26, 1994  | 1.0.0   |
February 14, 1994 | [1.0.1](https://github.com/di/vintage-python/tree/master/1.0.1) |
February 15, 1994 | 1.0.2   |
May 4, 1994       | 1.0.3   |
July 14, 1994     | 1.0.4   |
October 11, 1994  | [1.1](https://github.com/di/vintage-python/tree/master/1.1) |
November 10, 1994 | 1.1.1   |
April 13, 1995    | [1.2](https://github.com/di/vintage-python/tree/master/1.2) |
October 13, 1995  | [1.3](https://github.com/di/vintage-python/tree/master/1.3) |
October 25, 1996  | 1.4     |
January 3, 1998   | 1.5     |
October 31, 1998  | 1.5.1   |
April 13, 1999    | 1.5.2   |
September 5, 2000 | 1.6     |
October 16, 2000  | 2.0     |
February 25, 2001 | 1.6.1   |
April 17, 2001    | 2.1     |
December 21, 2001 | 2.2     |
July 29, 2003     | 2.3     |
November 30, 2004 | 2.4     |
September 16, 2006 | 2.5     |
October 1, 2008   | 2.6     |
December 3, 2008  | 3.0     |

If you have access to any missing releases at or below 1.0.0, please
[file an issue](https://github.com/di/vintage-python/issues/new)!
