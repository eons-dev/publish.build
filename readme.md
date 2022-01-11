# EBBS Publish Builder

This script is meant to be used by [ebbs](https://github.com/eons-dev/bin_ebbs)

In order to publish to the infrastructure.tech package repository, you must specify:
```shell
--repo-username
--repo-password
--version
```
and, optionally:
```shell
--visibility
--packageType
--description
```

You may also specify `--repo-url` if you want to use a different repository.
For an example of how to build your own repo, check out the [infrastructure.tech webserver](https://github.com/infrastructure-tech/srv_infrastructure)

When publishing your code, you can use `--visibility 'private'` or `--visibility 'public'`. Anything other than `private` or `public` will fail (unless you build your own repository api).
The `--packageType` parameter is a placeholder for now. It may be used in a future release, when packages become more complex.
The `--description` will be shown on the package page (once one is built; the front end of infrastructure.tech is still being built at the time of writing).

## What Publishing Entails

When you go to Publish a package, you must specify a folder within an eons-compliant (see [eons naming conventions](https://eons.dev/convention/naming/) and [eons directory conventions](https://eons.dev/convention/uri-names/)) directory.
That folder will become the "package". It will be zipped, then base64 encoded and sent off to the `{repo-url}/publish` endpoint with whatever args have been given as a json string.

You can view published packages at https://infrastructure.tech/package

NOTE: if you would like to privately publish packages, please contact support@infrastructure.tech. We'll be happy to create you an account and make sure our tools are suited to your use case :)

Once the Infrastructure front end is fully built, there will be a registration page where you'll be able to sign up yourself.