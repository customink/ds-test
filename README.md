
# Docker Sync Test

Simple setup with [docker-sync](http://docker-sync.io) to make sure it is working right. The patterns here are the basics of how Custom Ink uses this tool in combination with docker compose.

For details, see this [Serverless Docker Patterns](https://dev.to/aws-heroes/serverless-docker-patterns-4g1p) post.

## Setup & Test

Here is how to confirm docker-sync is working for you. First close and setup this repo as you would any normal strap-style project.

```shell
$ ./bin/bootstrap
$ ./bin/setup
```

Now to test that `docker-sync` is working as expected. Run the `bin/test` file.

```shell
$ ./bin/test
Creating ds-test_dstest_run ... done
1
```

Now change the `app.rb` file's contents to `puts '2'` and run `bin/test` again. If `docker-sync` is working, you should see:

```shell
$ ./bin/test
Creating ds-test_dstest_run ... done
2
```

## Issues?

Make sure you have `gRPC-FUSE` turned on under Preferences -> Expeirmental Features. This has been enabled for all stable/edge Docker Desktop for Mac releases.

* [Can `docker-edge` work without gRPC-FUSE?](https://github.com/EugenMayer/docker-sync/issues/755)
* [Is gRPC-FUSE really slow?](https://github.com/customink/docker-rails-lambda#benchmark)
