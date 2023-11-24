# Cade

Cade (Charm's Automated Development Environment) is an attempt at making a scripted environment suitable for the development and testing of charms.  

## Overview

Cade is a versatile shell script designed to simplify the setup and management of a charm development environment using Multipass. It automates the process of creating a virtual machine (VM), installing necessary packages, configuring users, and setting up tools like Docker, Juju, and MicroK8s. The script is ideal for developers working on charm development, providing a consistent and isolated environment.  

## Goals

- only one POSIX shell script
- multipass should be the only requirement
- mounts the developer's home directory to bring his tooling in the env
- focused on juju: any version should be installable
- easy deployment of multiple types of clouds

This is very much a work in progress.

## Installation

1. Copy the script to a desired location in your `PATH`.
2. Ensure the script is executable: `chmod +x <script_name>`.

## Help

```
Usage:
  cade expose <port>
  cade unexpose
  cade clean
  cade stop
  cade

Options:
  expose <port>      Set up an SSH tunnel from the host to the VM on the specified port.
  unexpose           Terminate the SSH tunnel for the Cade VM.
  clean              Purge and remove Cade instance and its associated files, after confirmation.
  stop               Stop the Cade instance.
                     (No option) Starts or initializes the Cade instance if not already done.

Notes:
  - `cade expose` sets up an SSH tunnel from the host machine to the Cade instance on the specified port.
  - `cade unexpose` kills the SSH tunnel process for the exposed port.
  - `cade clean` offers a prompt for confirmation before deleting the instance and associated files.
  - Running `cade` with no arguments ensures that the Cade instance is running, mounts the user's home directory, and starts an interactive shell within the instance.
```
