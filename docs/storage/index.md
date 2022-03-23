# Overview

[lustre]: parallel/lustre.md
[lumif]: parallel/lumif.md 
[lumip]: parallel/lumip.md 

The table below gives you an overview of the available options for storage. Note
that, except for the user home directory, data storage is allocated per project.

|                       | Quota | Max files | Expandable   | Backup | Retention        |
|:---------------------:|-------|-----------|:------------:|--------|------------------|
| User<br>Home          | 20 GB | 100k      | No           | Yes    | User lifetime    |
| Project<br>Scratch    | 50 TB | 2000k     | Yes<br>500TB | No     | 90 days          |
| Project<br>Persistent | 50 GB | 100k      | Yes<br>500GB | No     | Project lifetime |
| Project<br>Fast       |  2 TB | 1000k     | Yes<br>100TB | No     | 30 days          |

When a storage space is marked as expandable, it means that you can request 
more space if needed.

!!! failure "LUMI-F unavailable until summer 2022"

    To prepare for the installation of LUMI-G, LUMI-F has been removed from the
    system and will be available again after LUMI-G installation is completed.

!!! failure "Data rentention policies not active"

    Scratch automatic cleaning is not active at the moment. Please remove the 
    files that are no longer needed by your project on a regular basis if you 
    don't want to run out of TB-hours.

## Billing

Storage is billed by volume as well as time. The billing units are TB-hours. For
the regular scratch file system, 1TB that stays for 1 hour on the filesystem, 
consumes 1TB-hour. For the flash based filesytem 1TB for 1 hour consumes 
10 TB-hours.

## User Home

Each user has a home directory (`$HOME`) that can contain up to 20 GB of data. 
It is intended to store user configuration files and personal data. **You are
NOT supposed to run jobs from your home directory**.

The user home directory is purged once the user account expire.

## Project Persistent Storage

The Project Persistent storage is intended to share data amongst the members of
a project. You can see this workspace as the project home directory. Typically, 
this space can be used to share applications and libraries compiled for the 
project. **Just like the user home directory you are NOT supposed to run jobs 
from your the project persistent space**.

The project persistent storage is located at `/project/project_<project-number>`.

The project persistent directory is purged once the project expire.

## Parallel Filesystems (Scratch)

!!! failure "LUMI-F unavailable until summer 2022"

    To prepare for the installation of LUMI-G, LUMI-F has been removed from the
    system and will be available again after LUMI-G installation is completed.

The scratch spaces are Lustre file systems intended as **temporary** storage for
input, output or checkpoint data of your application. LUMI offers 2 types of 
scratch storage solution: LUMI-P with spinning disks and LUMI-F based on flash 
storage.

- [Learn more about Lustre][lustre]
- [Learn more about the Project Scratch storage][lumip]
- [Learn more about the Project Fast storage][lumif]

## Object Storage

Not available yet

|                 | Quota | Max buckets | Objects/bucket | Backup | Retention                      |
|-----------------|-------|-------------|----------------|--------|--------------------------------|
| Object Storage  | 10 TB | 1000        | 500K           | No     | Project lifetime<br> + xx days |

