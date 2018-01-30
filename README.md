# Quick Start

```shell
docker-compose up -d
```

The tests can take a while to run, perhaps an hour on a typical VM or laptop.

The tests will write results in the `./test-output` directory. You can change this directory by editing the `docker-compose.yml` file. At the end of the testing process will be a `compare.html` in the `test-output` directory that you can open in a web browser. The `docker-compose.yml` file also references nginx so if running on a VM and port `80` is open, you can access the results with something like:

<http://123.456.789.000/compare.html>


# Parameterizations

A couple of different parameterizations option are possible:

-   The THREDDS Server domain you wish to test (e.g., `thredds.ucar.edu` or `thredds-jetstream.unidata.ucar.edu`).
-   Whether you wish to test the IDV nightly build.

See the `compose.env` file to parameterize.


# Adding New Tests

Add the bundle to `idv-test/bundles/` and the expected images to `idv-test/baseline/`. Expected test images can be generated with the `testIDV` (next to the `runIDV`) executable. If the new bundle requires static test data, put it [here](http://ramadda.unidata.ucar.edu/repository/entry/show?entryid=55e76d1d-a970-463e-8e41-bd37318f46c2). In your bundle, point the IDV to `/tmp/data/` to find your test data.
