# Eser's AWS Lambda Base Images

This repository provides custom-built base images for AWS Lambda, focusing on offering more up-to-date project versions than those available in the official AWS Lambda base image repository.

My initial motivation was to provide the latest versions of projects that are not yet available or quickly updated in AWS's official offerings.

## What's Provided?

These images are built to be compatible with the AWS Lambda environment and include:

*   Official Debian base images.
*   The Lambda Runtime Interface Client (RIC).

## Available Images

Images are published to Docker Hub under my profile: [https://hub.docker.com/u/eserozvataf](https://hub.docker.com/u/eserozvataf)

The following images are available or in development:

| Project   | Version | Docker Image                 | Docker Hub Link                                                                    |
| :-------- | :------ | :--------------------------- | :--------------------------------------------------------------------------------- |
| Node.js   | 24.x    | `eserozvataf/nodejs-lambda:24` | [eserozvataf/nodejs-lambda:24](https://hub.docker.com/r/eserozvataf/nodejs-lambda/tags?name=24) |
| Deno      | TBD     | `eserozvataf/deno-lambda:latest` (example) | (Coming Soon)                                                                      |

*   The Node.js image is located in the `nodejs-lambda` directory in this repository. It includes a primary Dockerfile and examples for simple and multi-stage builds.
*   An image for the Deno runtime is currently in development.

## Usage

You can use these images by pulling them from Docker Hub or by building them locally.

### Pulling from Docker Hub

To use a pre-built image, you can pull it from Docker Hub:

```bash
docker pull eserozvataf/nodejs-lambda:24
```

Then, you can use `eserozvataf/nodejs-lambda:24` as the base image in your application's `Dockerfile`.

### Building an Image Locally

**Requirements:**

*   [git](https://git-scm.com/downloads)
*   [docker](https://docs.docker.com/get-docker/)

1.  **Clone this repository:**
    ```bash
    git clone <your-repository-url>
    cd docker-base-images
    ```

2.  **Navigate to the desired image directory:**
    For example, for Node.js:
    ```bash
    cd nodejs-lambda
    ```

3.  **Build the image:**
    ```bash
    docker build -t custom-nodejs-lambda:latest -f Dockerfile .
    ```
    This will use the `Dockerfile` in the current directory (e.g., `nodejs-lambda/Dockerfile`) and tag the newly-built image as `custom-nodejs-lambda:latest`.

    You can also refer to `Dockerfile.simple-usage` and `Dockerfile.multistage-usage` for examples on how to integrate these base images into your own application's Dockerfile.

## Maintenance and Updates

I aim to keep these images updated with the latest stable releases of the respective projects. Security patches and other necessary updates will be applied as they become available.

Since this project is driven by the need for newer versions, expect more frequent updates to projects versions compared to official images, where applicable.

## License

This project is licensed under the Apache-2.0 License. See [LICENSE](LICENSE) file for details.
