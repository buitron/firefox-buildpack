# Heroku buildpack: Firefox

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) for [Firefox](http://www.mozilla.org/en-US/firefox/new/). Meant to be used in combination with something like xvfb, for headless operation.

# Usage

Example usage:

```shell
$ heroku create --stack cedar --buildpack http://github.com/buitron/firefox-buildpack

# or if your app is already created:
$ heroku config:add BUILDPACK_URL=http://github.com/buitron/firefox-buildpack

$ git push heroku master
```

# Configuring the downloaded version of Firefox

By default, this buildback will download the latest release which is provided
by [Firefox](https://www.mozilla.org/en-US/firefox/releases/).

You can control the specific version by setting the `FIREFOX_VERSION` variable to an explicit version e.g. `63.0`.

## Note

If you're using [heroku-buildpack-multi](https://devcenter.heroku.com/articles/using-multiple-buildpacks-for-an-app) to include other buildpacks, you should set environment variable by your own to include following paths.

    PATH="/usr/local/bin:/usr/bin:/bin:/app/vendor/firefox"
    LD_LIBRARY_PATH="/usr/local/lib:/usr/lib:/lib:/app/vendor/firefox"


## Credit

I cloned a portion of this code from @bensomers so that I can configure the variables to create a recent buildpack for Heroku.
