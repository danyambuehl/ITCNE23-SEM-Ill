---
layout: default
#layout: minimal
title: Testing
nav_order: 4
---

## Testing und Probleme

![Testing](../img/testing.png)

| Description | Test Step | Expected Result | Status | Screen |
| ---         | ---       | ---             | ---    |  ---   |
| `PRTG`| Pause PRTG Monitoring with Ansible | Device Paused  | Device Paused | [Screenshot](../img/testing/prtg_pause_awx.png) |
| `PRTG`| Pause PRTG Monitoring in PRTG Tool | Device Paused  | Device Paused | [Screenshot](../img/testing/prtg_pause_prtg.png) |
| `PRTG`| Resume PRTG Monitoring with Ansible | Device Resumed  | Device Resumed | [Screenshot](../img/testing/prtg_resume_awx.png) |
| `PRTG`| Resume PRTG Monitoring in PRTG Tool | Device Resumed  | Device Resumed | [Screenshot](../img/testing/prtg_resume_prtg.png) |
| `Veeam M365`| Check for Running Jobs with Ansible | Error: Job is Running  | Error: Job is Running | [Screenshot](../img/testing/m365_job_status_failed.png) |
| `Veeam M365`| Check for Running Jobs in Veeam M365 | Error: Job is Running  | Error: Job is Running | [Screenshot](../img/testing/m365_job_status_failed2.png) |
| `Veeam M365`| Check for Running Jobs with Ansible | no running Jobs  | no running Jobs | [Screenshot](../img/testing/m365_job_status_free.png) |
| `WebHook`| Team News from Job start and finish | Success Message  | Success Message  | [Screenshot](../img/testing/web_hook.png) |
| `WebHook`| Team News from Job start and Error | ERROR Message  | ERROR Message  | [Screenshot](../img/testing/web_hook2.png) |
| `DiskSpace`| Check free space in 'C' and Error  | Error when lower than 15GB  | ERROR Message  | [Screenshot](../img/testing/disk_space.png) |
| `Veeam VBR`| CHECK FOR JOBS ON VBR SERVER  | Wait when Job is running  | Waiting  | [Screenshot](../img/testing/job_run1.png) |

Full Output Exports from AWX:

[ablauf_log.md](../07_Ablauf_Log/index.md)