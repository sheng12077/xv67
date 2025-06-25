# Guide to Students

## xv6 Overview

xv6 is a simple Unix-like operating system developed for educational purposes. It is designed to be small and easy to understand, making it an ideal platform for learning about operating systems.

## Git Overview

Git is a version control system that allows you to track changes in your code and collaborate with others.

We will use Git to manage our xv6 codebase, any updates to the template will be pushed to the repository, and we will announce if there are any changes.

Learn to cooperate with your team members using Git.

## How to run xv6

### Run on your local machine

1. Clone the repository and navigate to the directory:

    ```bash
    cd xv6-Template
    ```

2. Install the required dependencies
3. Start xv6:

    ```bash
    make qemu
    ```

    This will start the xv6 operating system in a QEMU virtual machine.

4. To quit xv6, press `<Ctrl+a x>`.

### Run with Docker (Recommended)

Running with Docker offers a convenient way to set up your environment without installing dependencies directly on your machine. While its performance (execution time) might not match native execution, it generally won't compromise correctness.

1. Clone the repository and navigate to the directory:

    ```bash
    cd xv6-Template
    ```

2. Pull the built image:

    ```bash
    # For amd64 architecture (e.g., most Intel/AMD processors):
    docker pull dasbd72/xv6:amd64
    # For arm64v8 architecture (e.g., Apple Silicon):
    docker pull dasbd72/xv6:arm64v8
    ```

3. Run the Docker container with the following command:
    1. For MacOS and Linux:

        ```bash
        # For amd64 architecture (e.g., most Intel/AMD processors):
        docker run -it --rm -v $(pwd):/xv6 -v /xv6/mkfs -v $(pwd)/mkfs/mkfs.c:/xv6/mkfs/mkfs.c -w /xv6 --platform linux/amd64 dasbd72/xv6:amd64
        # For arm64v8 architecture (e.g., Apple Silicon):
        docker run -it --rm -v $(pwd):/xv6 -v /xv6/mkfs -v $(pwd)/mkfs/mkfs.c:/xv6/mkfs/mkfs.c -w /xv6 --platform linux/arm64/v8 dasbd72/xv6:arm64v8
        ```

    2. For Windows PowerShell:

        ```bash
        # For amd64 architecture (e.g., most Intel/AMD processors):
        docker run -it --rm -v ${PWD}:/xv6 -v /xv6/mkfs -v ${PWD}/mkfs/mkfs.c:/xv6/mkfs/mkfs.c -w /xv6 --platform linux/amd64 dasbd72/xv6:amd64
        # For arm64v8 architecture (e.g., Apple Silicon):
        docker run -it --rm -v ${PWD}:/xv6 -v /xv6/mkfs -v ${PWD}/mkfs/mkfs.c:/xv6/mkfs/mkfs.c -w /xv6 --platform linux/arm64/v8 dasbd72/xv6:arm64v8
        ```

    3. For Windows CMD:

        ```bash
        # For amd64 architecture (e.g., most Intel/AMD processors):
        docker run -it --rm -v %cd%:/xv6 -v /xv6/mkfs -v %cd%/mkfs/mkfs.c:/xv6/mkfs/mkfs.c -w /xv6 --platform linux/amd64 dasbd72/xv6:amd64
        # For arm64v8 architecture (e.g., Apple Silicon):
        docker run -it --rm -v %cd%:/xv6 -v /xv6/mkfs -v %cd%/mkfs/mkfs.c:/xv6/mkfs/mkfs.c -w /xv6 --platform linux/arm64/v8 dasbd72/xv6:arm64v8
        ```

4. Start xv6:

    ```bash
    make qemu
    ```

    This will start the xv6 operating system in a QEMU virtual machine.

5. To quit xv6, press `<Ctrl+a x>`.
6. To exit the Docker container, type `exit` in the terminal.
