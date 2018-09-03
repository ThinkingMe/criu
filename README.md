[![master](https://travis-ci.org/checkpoint-restore/criu.svg?branch=master)](https://travis-ci.org/checkpoint-restore/criu)
[![development](https://travis-ci.org/checkpoint-restore/criu.svg?branch=criu-dev)](https://travis-ci.org/checkpoint-restore/criu)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/55251ec7db28421da4481fc7c1cb0cee)](https://www.codacy.com/app/xemul/criu?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=xemul/criu&amp;utm_campaign=Badge_Grade)
<p align="center"><img src="https://criu.org/w/images/1/1c/CRIU.svg" width="256px"/></p>

## CRIU for Android -- A project to implement checkpoint/restore functionality for Android

CRIU (stands for Checkpoint and Restore in Userspace) is a utility to checkpoint/restore Linux tasks.
  http://criu.org
  https://github.com/checkpoint-restore/criu

However, it is not enough just support for Linux tasks, in some case, people want to use CRIU to checkpoint/restore Android tasks. Besides, for some special cases, people want to checkpoint/restore a process tree including Linux tasks and Android tasks.

## Mission and Future
  1. Release a criu variance for Android;
     Build a criu variance that can be run on Android
     
  2. Make criu to support checkpoint/restore Android runtime;
     Android runtime have different libc and pthread implementation compare with generic Linux runtime

  3. Make criu to support checkpoitn/restore configfs;
     Android use configfs for usb devices

  4. Make criu to support checkpoint/restore binder device (Binder IPC);
     Kernel: Export binder information to /proc/<pid>/binder
     CRIU: Support binder type device and support binder ops replay

  5. Upstream the feature of checkpoint/restore Android runtime to original CRIU branch.
     Make criu to identify the glibc-based runtime and bionic-based runtime at runtime.
     In some case, especially for container, maybe the root process is Linux runtime, but the child is Android runtime,
     Make criu to support checkpoint/restore the process tree mixed Linux runtime (Glibc-based) and Android runtime;

## Licence

The project is licensed under GPLv2 (though files sitting in the lib/ directory are LGPLv2.1).
