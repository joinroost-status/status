# Roost Status

This repository broadcasts the status of the Roost system for use in its frontend.

It is in a GitHub repository, far away from Roost's normal infrastructure, as a redundancy measure.

## Format

The status files are JSON, and have the following keys:

| Key       | Value                                                                                                                                            |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| `status`  | The status of the system, either:                                                                                                                |
|           | `UP`: the system is up and running; `message` is ignored                                                                                         |
|           | `INFO`: the app is functioning normally but an informational; `message` is shown in the app in a banner with a blue background treatment         |
|           | `DEGRADED`: the system has some issue, but it is still navigable; `message` is shown in the app in a banner with a red background treatment      |
|           | `MAINTENANCE`: the system is fully down, all routes display a full-bleed splash-screen showing the `message` under a "Maintenance" header        |
|           | `OUTAGE`: the system is fully down, all routes display a full-bleed splash-screen showing the `message` under a "Temporary outage" header        |
| `message` | The message to be shown, in plain text                                                                                                           |

## Environments

Status files for the following environments are supported:

| Environment | Description                  |
|-------------|------------------------------|
| Local       | Local developer use          |
| Staging     | Staging and test environment |
| Production  | Production environment       |

