# Reithbot Main Monorepo

Monorepo to Manyrepo Split Build [![Monorepo Split Status](https://travis-ci.org/reithbot/main.svg?branch=master)](https://travis-ci.org/reithbot/main)

## Build Process - Monorepo to Manyrepo
Development is conducted in this repo. Then when commits are pushed up
[travis](https://travis-ci.org/reithbot/main) runs and uses the
[jderusse/docker-gitsplit](https://github.com/jderusse/docker-gitsplit) docker container to then run
[splitsh-lite](https://github.com/splitsh/lite). This in turn sends commits off to our
[toyrobot-php](https://github.com/reithbot/toyrobot-php) mini-repo. Note that the root of the toyrobot-php repository is
the `./php/` path in this repo.

Receiving commits in the **toyrobot-php** repo triggers further builds to ensure quality is maintained. See the [README
there](https://github.com/reithbot/toyrobot-php#infrastructure) about those builds.

Here is an example of a build where the split took place:

* https://travis-ci.org/reithbot/main/builds/368205988
