---
title: "LTP"
date: 2021-07-21T13:30:00Z
draft: true
description: "Native tests: LTP"
---

## About

The [Linux Test Project](https://linux-test-project.github.io/) is one of the
major open-source test suites for Linux systems at large.  Only a subset of it
is being run by KernelCI, to focus on the ones that appear to be the most
relevant to kernel testing.

A series of Debian Buster user-space images to run these tests are being built
regularly, typically once a week.  They contain all of LTP from the latest
version of the `master` branch built from source.  They are stored on the
[KernelCI storage
server](https://storage.kernelci.org/images/rootfs/debian/buster-ltp/?C=M&O=D).

## KernelCI coverage

Initial GitHub issue: [#506](https://github.com/kernelci/kernelci-core/issues/506)

The table below shows a summary of the current KernelCI LTP coverage per CPU
architecture and platform for each subset.  Until a more dynamic orchestration
becomes available, this is all defined in
[`test-configs.yaml`](https://github.com/kernelci/kernelci-core/blob/master/test-configs.yaml).
The goal is to have each LTP subset run on at least 2 platforms of each CPU
architecture.  All these tests are typically run on every kernel revision built
by KernelCI, except for trees filtered out by labs or if the kernel is too old
to support the platform.


| Platform                  | arch    | crypto | ima | ipc | locktests | mm | pty | timers |
|---------------------------|---------|--------|-----|-----|-----------|----|-----|--------|
| asus-C523NA-A20057-coral  | x86\_64 | ✔      | ✔   | ✔   | ✔         | ✔  | ✔   | ✔      |
| bcm2836-rpi-2-b           | arm     | ✔      |     |     |           |    |     |        |
| beaglebone-black          | arm     |        |     | ✔   |           |    |     |        |
| hp-11A-G6-EE-grunt        | x86\_64 | ✔      |     | ✔   | ✔         | ✔  | ✔   | ✔      |
| hp-x360-12b-n4000-octopus | x86\_64 | ✔      |     | ✔   |           | ✔  |     |        |
| mt8173-elm-hana           | arm64   | ✔      |     | ✔   | ✔         | ✔  | ✔   | ✔      |
| rk3288-rock2-square       | arm     |        |     |     |           | ✔  |     |        |
| rk3288-veyron-jaq         | arm     |        |     |     |           |    |     | ✔      |
| rk3399-gru-kevin          | arm64   |        |     |     | ✔         |    | ✔   | ✔      |
| sun50i-h6-pine-h64        | arm64   | ✔      |     | ✔   |           | ✔  |     |        |