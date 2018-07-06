# runhcs

## Introduction

`runhcs` is a fork of [runc](https://github.com/opencontainers/runc) modified to run on Windows and provide support for the various HCS-based containers available on Windows.  Like runc, runhcs is a CLI tool for spawning and running containers according to the OCI specification.

## Releases

`runhcs` is currently under development.  Like `runc`, `runhcs` will track the [OCI runtime-spec](https://github.com/opencontainers/runtime-spec) so `runhcs` and the OCI specification major versions stay in lockstep.

For example:  
`runc` 1.0.0 should implement the 1.0 version of the specification.

## Building

See [hcsshim build instructions](../../README.md).

## Using runhcs

### Creating an OCI Bundle

In order to use runc you must have your container in the format of an OCI bundle.

### Running Containers

Assuming you have an OCI bundle from the previous step you can execute the container in two different ways.

The first way is to use the convenience command `run` that will handle creating, starting, and deleting the container after it exits.

```bash
# run as root
cd /mycontainer
runc run mycontainerid
```

If you used the unmodified `runc spec` template this should give you a `sh` session inside the container.
