# Roost Status

This repository broadcasts the status of the Roost system for use in its frontend.

It is in a GitHub repository, far away from Roost's normal infrastructure, as a redundancy measure.

## Format

The status files are JSON, and have the following keys:

| Key       | Value                                                                                                                                            |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| `status`  | The status of the system, either:                                                                                                                |
|           | `UP`: the system is up and running; `message` is ignored                                                                                         |
|           | `INFO`: the app is functioning normally but an informational; `adminMessage` or `residentMessage` is shown in the app in a banner with a blue background treatment         |
|           | `DEGRADED`: the system has some issue, but it is still navigable; `adminMessage` or `residentMessage` is shown in the app in a banner with a red background treatment      |
|           | `MAINTENANCE`: the system is fully down, all routes display a full-bleed splash-screen showing the `maintenanceMessage` under a "Maintenance" header        |
|           | `OUTAGE`: the system is fully down, all routes display a full-bleed splash-screen showing a hard-coded message under a "Temporary outage" header        |
| `maintenanceMessage` | The message to be shown when the status is MAINTENANCE, in plain text                                                                                                           |
| `adminMessage` | The message to be shown in the admin hub when the status is INFO or DEGRADED, in plain text                                                                                                           |
| `residentMessage` | The message to be shown in the resident app when the status is INFO or DEGRADED, in plain text                                                                                                           |

## Environments

Status files for the following environments are supported:

| Environment | Description                  |
|-------------|------------------------------|
| Local       | Local developer use          |
| Staging     | Staging and test environment |
| Production  | Production environment       |
