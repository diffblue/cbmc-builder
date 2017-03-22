This is the Git repo of the Docker images for building
[CBMC](https://github.com/diffblue/cbmc) in/for different operating systems.                        

To compile `CBMC` source

```bash
CBMC_PATH=~/Workspace/cbmc-git
docker run --rm -v ${CBMC_PATH}:/cbmc diffblue/cbmc-builder make -C src minisat2-download
docker run --rm -v ${CBMC_PATH}:/cbmc diffblue/cbmc-builder make -C src libzip-download zlib-download
docker run --rm -v ${CBMC_PATH}:/cbmc diffblue/cbmc-builder make -C src libzip-build
docker run --rm -v ${CBMC_PATH}:/cbmc diffblue/cbmc-builder make -C src -j2
```

To run tests afterwards

```bash
docker run --rm -v ${CBMC_PATH}:/cbmc diffblue/cbmc-builder make -C regression test
```
