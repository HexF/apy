# apy

APY is a collection of useful APIs.

## Motivation

My motivations for this project are to unify common APIs together to create an api-ecosystem, as well as create a bunch of new useful APIs.

One example of a new API would be finding an ISO for an Operating System.
You could simply `curl https://apy.nz/os/linux/ubuntu/20.04/` and get download information for Ubuntu 20.04
Alternatively, you could `curl https://apy.nz/os/linux/ubuntu/latest/` and get information about the latest version of Ubuntu.

## Specifications

All APY APIs are based on the same specifications, which you can view [here](SPECS.MD).

The TL;DR is that all APIs should
1. provide documentation when `?help` is added to the url
  1. If &json is added, serve the documentation in JSON form
  2. If the client is command line, serve documentation in text form. This can also be called with `&text`
  3. If the client is a web browser, serve the documentation in HTML form.
2. only take paramters in the URL
3. be stateless. This means
  1. no data persistance
  2. the user shouldn't need to be served by the same server twice.
  3. any data that is required is either compiled into the binary, or fetched from an external API.
4. Be in Docker Container
5. Contain an Apyfile

## Licencing

This is an open source API, however hosting an API does incur some costs of which need to be paid for some how.
This means we have to some how licence our API. We do this with rate limits.
The API imposes some rate limits, of 5000 requests per week per IP (roughly 30 requests an hour for a whole week).
If you need more that 5000 requests a week, you can provide a monthly donation and get an API key, which will allow you to increase your limits.

