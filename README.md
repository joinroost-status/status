# Roost Status

This repository broadcasts the status of the Roost system for use in its frontend.

It is in a GitHub repository, far away from Roost's normal infrastructure, as a redundancy measure.

## Format

The status files are JSON, and have the following keys:

| Key       | Value                                                                                                                                            |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| `status`  | The status of the system, either:                                                                                                                |
|           | `UP`: the system is up and running; `message` is ignored                                                                                         |
|           | `DEGRADED`: the system has some issue, but it is still available at some level; `message` is shown in the app                                    |
|           | `DOWN`: the system is fully down, and users should not be allowed in; `message` is shown prominently in the app instead of the ability to log in |
| `level`   | The severity level to be expressed by message. This probably translates in the styling of the message:                                           |
|           | `RED`                                                                                                                                            |
|           | `GREEN`                                                                                                                                          |
|           | `YELLOW`                                                                                                                                         |
| `message` | The message to be shown, in plain text                                                                                                           |

## Environments

Status files for the following environments are supported:

| Environment | Description                  |
|-------------|------------------------------|
| Local       | Local developer use          |
| Staging     | Staging and test environment |
| Production  | Production environment       |
