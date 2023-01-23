## The Update Framework (TUF) client
This repository contains a very basic TUF client, the sole purpose of this is
document and understand how a TUF client works.

### Installing tuftool
This example is going to use a tool called
[tuftool](https://github.com/awslabs/tough/tree/develop/tuftool) to create the
example TUF repository that will be used by the example. It can be installed
using the following command:
```console
$ cargo install --force tuftool
```

### Generating the TUF repository
And we can generate root.json, the private and public key used for
signing/verification, and the TUF repository using the following script:
```console
$ ./tuftool.sh
```
After this command has been run the TUF repository will be created a directory
named `tuf_repo`, and the `keys` directory will contain the private key.

### Usage
The example uses the [tough](https://crates.io/crates/tough) library, and
starts by loading the repository, and after that downloading an artifact
named `artifact.txt` from the TUF repository and printing out the contents:
```console
$ cargo r --quiet -- --repo-dir tuf_repo --trusted-root-json tuf_client/root.json --download-dir tuf_client
TUF client example...
Tring to fetch artifact.txt from TUF repository
Fetched artifact.text: "something\n"
```
