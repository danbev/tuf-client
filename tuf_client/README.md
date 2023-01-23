## tuf_client dirctory
This is the directory where TUF client metadata files will be downloaded to.

There is a `root.json` file in this directory and the only purpose having it
is to visualize what the initial state of a client is. This root.json is
simulating the [trusted root metadata file](https://theupdateframework.github.io/specification/latest/index.html#load-trusted-root).

When the example is run this directory will get populated with addition metadata
files downloaded from the TUF repository.
