<!--

********************************************************************************

WARNING:

    DO NOT EDIT "elixir/README.md"

    IT IS AUTO-GENERATED

    (from the other files in "elixir/" combined with a set of templates)

********************************************************************************

-->

# Supported tags and respective `Dockerfile` links

-	[`1.5.0`, `1.5`, `latest` (*1.5/Dockerfile*)](https://github.com/c0b/docker-elixir/blob/44078809bd868e654d93766f8ac3c778f688a951/1.5/Dockerfile)
-	[`1.5.0-slim`, `1.5-slim`, `slim` (*1.5/slim/Dockerfile*)](https://github.com/c0b/docker-elixir/blob/a57ae22bc9505ccdc7662f2556143e1048361d47/1.5/slim/Dockerfile)
-	[`1.5.0-alpine`, `1.5-alpine`, `alpine` (*1.5/alpine/Dockerfile*)](https://github.com/c0b/docker-elixir/blob/a57ae22bc9505ccdc7662f2556143e1048361d47/1.5/alpine/Dockerfile)
-	[`1.4.5`, `1.4` (*1.4/Dockerfile*)](https://github.com/c0b/docker-elixir/blob/8f1888ae05506b9ad12e1b97f084a15e7588f442/1.4/Dockerfile)
-	[`1.4.5-slim`, `1.4-slim` (*1.4/slim/Dockerfile*)](https://github.com/c0b/docker-elixir/blob/8f1888ae05506b9ad12e1b97f084a15e7588f442/1.4/slim/Dockerfile)
-	[`1.3.4`, `1.3` (*1.3/Dockerfile*)](https://github.com/c0b/docker-elixir/blob/d8d656d7c0dc9dd2956a22276c93cb97568ea6d4/1.3/Dockerfile)
-	[`1.3.4-slim`, `1.3-slim` (*1.3/slim/Dockerfile*)](https://github.com/c0b/docker-elixir/blob/d8d656d7c0dc9dd2956a22276c93cb97568ea6d4/1.3/slim/Dockerfile)
-	[`1.2.6`, `1.2` (*1.2/Dockerfile*)](https://github.com/c0b/docker-elixir/blob/77b9a3da43ce035327ae29083e567191d60a6ac8/1.2/Dockerfile)
-	[`1.2.6-slim`, `1.2-slim` (*1.2/slim/Dockerfile*)](https://github.com/c0b/docker-elixir/blob/77b9a3da43ce035327ae29083e567191d60a6ac8/1.2/slim/Dockerfile)

# Quick reference

-	**Where to get help**:  
	[the Docker Community Forums](https://forums.docker.com/), [the Docker Community Slack](https://blog.docker.com/2016/11/introducing-docker-community-directory-docker-community-slack/), or [Stack Overflow](https://stackoverflow.com/search?tab=newest&q=docker)

-	**Where to file issues**:  
	[https://github.com/c0b/docker-elixir/issues](https://github.com/c0b/docker-elixir/issues)

-	**Maintained by**:  
	[the Docker Community](https://github.com/c0b/docker-elixir), [with Elixir's support](https://github.com/docker-library/official-images/pull/1398#issuecomment-180484549)

-	**Published image artifact details**:  
	[repo-info repo's `repos/elixir/` directory](https://github.com/docker-library/repo-info/blob/master/repos/elixir) ([history](https://github.com/docker-library/repo-info/commits/master/repos/elixir))  
	(image metadata, transfer size, etc)

-	**Image updates**:  
	[official-images PRs with label `library/elixir`](https://github.com/docker-library/official-images/pulls?q=label%3Alibrary%2Felixir)  
	[official-images repo's `library/elixir` file](https://github.com/docker-library/official-images/blob/master/library/elixir) ([history](https://github.com/docker-library/official-images/commits/master/library/elixir))

-	**Source of this description**:  
	[docs repo's `elixir/` directory](https://github.com/docker-library/docs/tree/master/elixir) ([history](https://github.com/docker-library/docs/commits/master/elixir))

-	**Supported Docker versions**:  
	[the latest release](https://github.com/docker/docker/releases/latest) (down to 1.6 on a best-effort basis)

# What is Elixir?

Elixir is a dynamic, functional language designed for building scalable and maintainable applications.

Elixir leverages the Erlang VM, known for running low-latency, distributed and fault-tolerant systems, while also being successfully used in web development and the embedded software domain.

> [en.wikipedia.org/wiki/Elixir_(programming_language)](https://en.wikipedia.org/wiki/Elixir_%28programming_language%29)

![logo](https://raw.githubusercontent.com/docker-library/docs/f3ee5318992592f987a289cd72d63ac1807f569d/elixir/logo.png)

# How to use this image

## Run it as the REPL

```console
➸ docker run -it --rm elixir
Erlang/OTP 18 [erts-7.2.1] [source] [64-bit] [smp:8:8] [async-threads:10] [hipe] [kernel-poll:false]

Interactive Elixir (1.2.1) - press Ctrl+C to exit (type h() ENTER for help)
iex(1)> System.version
"1.2.1"
iex(2)>
➸ docker run -it --rm -h elixir.local elixir iex --sname snode
Erlang/OTP 18 [erts-7.2.1] [source] [64-bit] [smp:8:8] [async-threads:10] [hipe] [kernel-poll:false]

Interactive Elixir (1.2.1) - press Ctrl+C to exit (type h() ENTER for help)
iex(snode@elixir)1> System.version
"1.2.1"
iex(snode@elixir)2> :c.uptime
14 seconds
:ok
```

## Run a single Elixir exs script

```console
$ docker run -it --rm --name elixir-inst1 -v "$PWD":/usr/src/myapp -w /usr/src/myapp elixir elixir your-escript.exs
```

# Image Variants

The `elixir` images come in many flavors, each designed for a specific use case.

## `elixir:<version>`

This is the defacto image. If you are unsure about what your needs are, you probably want to use this one. It is designed to be used both as a throw away container (mount your source code and start the container to start your app), as well as the base to build other images off of.

## `elixir:slim`

This image does not contain the common packages contained in the default tag and only contains the minimal packages needed to run `elixir`. Unless you are working in an environment where *only* the `elixir` image will be deployed and you have space constraints, we highly recommend using the default image of this repository.

## `elixir:alpine`

This image is based on the popular [Alpine Linux project](http://alpinelinux.org), available in [the `alpine` official image](https://hub.docker.com/_/alpine). Alpine Linux is much smaller than most distribution base images (~5MB), and thus leads to much slimmer images in general.

This variant is highly recommended when final image size being as small as possible is desired. The main caveat to note is that it does use [musl libc](http://www.musl-libc.org) instead of [glibc and friends](http://www.etalabs.net/compare_libcs.html), so certain software might run into issues depending on the depth of their libc requirements. However, most software doesn't have an issue with this, so this variant is usually a very safe choice. See [this Hacker News comment thread](https://news.ycombinator.com/item?id=10782897) for more discussion of the issues that might arise and some pro/con comparisons of using Alpine-based images.

To minimize image size, it's uncommon for additional related tools (such as `git` or `bash`) to be included in Alpine-based images. Using this image as a base, add the things you need in your own Dockerfile (see the [`alpine` image description](https://hub.docker.com/_/alpine/) for examples of how to install packages if you are unfamiliar).

# License

Copyright 2012 Plataformatec

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at

View [license information](http://www.apache.org/licenses/LICENSE-2.0) for the software contained in this image.

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.
