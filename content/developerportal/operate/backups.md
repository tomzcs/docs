---
title: "Backups"
category: "Operate"
description: "This page describes the Backups page of the Developer Portal."
tags: ["Operate","App","Developer Portal","Backup"]
---

## 1 Introduction

Backups in the Mendix Cloud have two parts: database and file documents. A backup is created every night or on-demand, as described in [3 Backups](#Backups). For the database, a full backup is made. File documents are backed up incrementally. 

Additionally, a replication/failover add-on can be purchased that will enable incremental backups with a 15 minute interval for the database and file documents.

## 2 Nightly Backups – Creation and Retention Schedules

The pruning schedule applies to nightly backups and backups initiated by users. If you want to keep a backup for longer than scheduled, you will have to download it.

The following backups are retained:

* Last two weeks: every day
* Last three months: every Sunday
* Last year: every first Sunday of the month

The start time of the backup creation depends on the region and the Mendix Cloud version:

| Europe |  UTC (UTC) | CET (CET) |
| --- | --- | --- |
| Cloud v3 | 22:00 | 00:00 |
| Cloud v4 | 19:00 | 21:00 |

| US East |  UTC (UTC) | EST (EST) |
| --- | --- | --- |
| Cloud v3 | 05:00 | 01:00 |
| Cloud v4 | 01:00 | 21:00 |

| Asia Pacific |  UTC (UTC) | JST (JST) |
| --- | --- | --- |
| Cloud v4 | 16:00 | 01:00 |

## 3 Backups<a name="Backups"></a>

The **Backups** page under the **Operate** category presents options for managing your backups. These are described below.

### 3.1 Creating a Backup

This will automatically generate a backup from your application data.

### 3.2 Uploading Data

You must stop the application before executing this process. This functionality is used to transfer data from your local or on-premises application to the cloud environment. This will not add a backup to the backup list but directly update the application with the newly uploaded data. Your environment will be cleared completely. The deployment package, uploaded files, and database will be removed. If you are uploading data to the production environment, any published app services will be unpublished.

You can upload two types of data:

* **Database**
* **Uploaded files** (*zip* or *tar.gz*)

### 3.3 Restoring a Backup

You can choose the environment to which you want to restore the backup.

If you restore a backup that was originally deployed on an older Modeler version, you will get a warning. You can still restore the backup, but you have to deploy the older model later on. 

### 3.4 Downloading a Backup

These are the options:

* **Full Snapshot**
* **Database Only**
* **Files Only**

## 4 Backup Details

When you click **Details**, you can view the following details:

* **Status** – the status of the backup
  * Backups can have the status of **Queued**, **Running**, **Failed**, and **Completed**
* **Created by** – the name of the person who created the backup
  * Automated system backups are named **Nightly**
* **Date** – the creation date of the backup
* **Expires on** – the date on which the backup will be removed from the system
* **Model version** – the version of the deployment package used during backup creation
* **Comment** – a specific comment added to the backup

## 5 Related Content

* [Alerts](/developerportal/operate/monitoring-application-health)
* [Logs](/developerportal/operate/logs)
* [Metrics](/developerportal/operate/metrics)
* [Operate](/developerportal/operate)
