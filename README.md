# Cade

Cade (Charm's Automated Development Environment) is an attempt at making a scripted environment suitable for the development and testing of charms.  

## Goals
- only one POSIX shell script
- multipass should be the only requirement
- mounts the developer's home directory to bring his tooling in the env
- focused on juju: any version should be installable
- easy deployment of multiple types of clouds
- offline deployment (?)

This is very much a work in progress.

## Help

```
Usage:
  cade expose <port>
  cade unexpose
  cade clean
  cade stop
  cade

Options:
  expose <port>      Expose the specified port for the Cade instance.
  unexpose           Terminate the exposed port session for the Cade instance.
  clean              Purge and remove Cade instance and its associated files, after confirmation.
  stop               Stop the Cade instance.
                     (No option) Starts or initializes the Cade instance if not already done.

Notes:
  - `cade expose` sets up an SSH tunnel from the host machine to the Cade instance on the specified port.
  - `cade unexpose` kills the SSH tunnel process for the exposed port.
  - `cade clean` offers a prompt for confirmation before deleting the instance and associated files.
  - Running `cade` with no arguments ensures that the Cade instance is running, mounts the user's home directory, and starts an interactive shell within the instance.
```
