# Compile the port for QNX

**NOTE**: QNX ports are only supported from a Linux host operating system

- Setup your QNX SDP environment
- Build and install `googletest` first (tested version 1.13.0 with QNX changes)
- From the root folder, type:
  - `OSLIST=nto make -C qnx/build install`
