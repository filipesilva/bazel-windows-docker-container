## Repro instructions

Example of using bazel inside a windows docker container.

Note: these commands are for windows cmd.exe.

- Copy a `bazel.exe` binary to this folder.
- Build the docker image: `docker build -t bazel-windows-container:0.0.1 .`
- Run the image with this repro: `docker run -v %cd%:C:\src -it bazel-windows-container:0.0.1`
- Inside the container run:
```
cd src
bazel info
bazel build :shell_build 
```
- You can change the bazel binary on your host OS folder and it will change inside the container too.
