**Example of how to use nix binaries in bazel**

In this example, we write a target to run `pg_dump`, source from nix.

Requirements for running:
* ensure that you have [nix](https://nixos.org/download.html) installed
* ensure that you have [bazel](https://bazel.build/install) installed

To run:

```bash
$ bazel run //:pg_dump -- --version
INFO: Analyzed target //:pg_dump (0 packages loaded, 0 targets configured).
INFO: Found 1 target...
Target //:pg_dump up-to-date:
  bazel-bin/pg_dump
INFO: Elapsed time: 0.050s, Critical Path: 0.00s
INFO: 1 process: 1 internal.
INFO: Build completed successfully, 1 total action
INFO: Build completed successfully, 1 total action
pg_dump (PostgreSQL) 14.3
```

**Where to go from here**

You can search for other packages at [search.nixos.org](https://search.nixos.org)

**If you found this useful**

... drop me a line at [aryeh.fun](https://aryeh.fun)

