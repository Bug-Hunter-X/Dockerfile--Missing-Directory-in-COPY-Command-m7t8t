# Dockerfile Bug: Missing Directory

This repository demonstrates a common error in Dockerfiles: attempting to copy files into a non-existent directory. The provided `Dockerfile` attempts to copy a `requirements.txt` file into `/app`, but this directory is not created beforehand.

The solution demonstrates how to correct this by creating the `/app` directory using the `mkdir` command before the `COPY` command.

## How to Reproduce the Bug

1.  Clone this repository.
2.  Try to build the image using `docker build -t my-image .`
3.  Observe the build failure due to the missing directory.

## Solution

The solution involves creating the `/app` directory before the `COPY` command, ensuring the target directory exists before attempting to copy files into it.