# Readme

This is a set of examples supporting my Lightning Talk "A Tiny Talk on Tiny Containers" at KubeCon NA 2023.  
The talk demonstrates good practices and approaches for reducing container image size and is intended for cloud native beginners.  
The core points are to **refer the most minimal base image that fits your requirements** and **take advantage of multi-stage builds**.  
The examples in this repo are simple Go applications (the same in each example) with Dockerfiles that produce very different image sizes:  
* A single-stage build using the Go 1.21 Debian-based image produces an image that is 301.86 MB compressed.
* A single-stage build using the Go 1.21 Alpine-based image produces an image that is 85.79 MB compressed.
* A multi-stage build using Alpine as a base image for the final product creates an image that is 6.95 MB compressed.
* A multi-stage build using the "scratch" base image for the final product creates an image that is 3.71 MB compressed.  
The talk also discusses creating a Wasm module that runs on Kubernetes sized at 83.3 KB. You can learn more about the Wasm approach [here](https://vmblog.com/archive/2023/11/02/how-to-build-a-webassembly-on-kubernetes-development-environment-with-k0s-and-spin.aspx).
