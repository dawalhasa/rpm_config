---
title: How to build & configure RPM repository
author: Dawalhasa
---

RPM file structure
==================
```bash

                  -------------------------------------------------NAME
                  |         ---------------------------------------VERSION
                  |         |       -------------------------------RELEASE
                  |         |       |      ------------------------ARCH
                  |         |       |      |
                  |         |       |      |
                  |         |       |      |
                  |         |       |      |
            -----------  ------  -----  ------
            |          | |    |  |   |  |    |
            [HTTP/TOOLS]-[2.5.3]-[7.wd].[aarch].[rpm]
```
<!-- end_slide -->
Install Repository builder
==========================
<!-- new_line -->
<!-- pause -->
```bash
    sudo yum install rpm-build rpmdevtools -y
```
<!-- end_slide -->
Initialize the repository builder
=================================
<!-- new_line -->
<!-- pause -->
```bash
    rpmdev-setuptree
```
<!-- end_slide -->
Check the rpmbuild dictory using ls command
===========================================
<!-- new_line -->
<!-- pause -->
```bash +exec
    ls ~
```
<!-- end_slide -->
Change root to normal user
==========================
<!-- new_line -->
<!-- pause -->
```bash +exec
    su dawalhasa
```
<!-- end_slide -->
Rpmbuild directory exist than check using tree command
======================================================
<!-- new_line -->
<!-- pause -->
```bash +exec
    tree ~/rpmbuild
```
<!-- end_slide -->
Check rpmbuild file system
==========================
<!-- new_line -->
<!-- pause -->
```bash +exec
    ls -la ~/rpmbuild
```
<!-- end_slide -->
Create a directory for local rpm repository
===========================================
<!-- new_line -->
<!-- pause -->
```bash +exec
    mkdir local_rpo-1.0
```
<!-- end_slide -->
Change diretory to local repository
===================================
<!-- new_line -->
<!-- pause -->
```bash +exec
    cd local_repo-1.0
```
<!-- end_slide -->
Inside local rpm repository create config and document files
============================================================
<!-- new_line -->
<!-- pause -->
```bash +exec
    touch local_repo-1.0.conf
```
<!-- pause -->
```bash +exec
    touch local_repo-1.0.txt
```
<!-- end_slide -->
Create tar file using the local repository ditorory
===================================================
<!-- new_line -->
<!-- pause -->
```bash +exec
    tar czvf ~/rpmbuild/SOURCES/local_repo-1.0-1.tar.gz $HOME/local_repo-1.0
```
<!-- end_slide -->
Check rpmbuild dictory whether the tar file is build or not
===========================================================
<!-- new_line -->
<!-- pause -->
```bash +exec
    ls rpmbuild/SOURCES
```
<!-- end_slide -->
Change directory to rpmbuild/SPECS
==================================
<!-- new_line -->
<!-- pause -->
```bash +exec
    cd rpmbuild/SPECS
```
<!-- end_slide -->
Use rpmdev and build spec file
==============================
<!-- new_line -->
<!-- pause -->
```bash +exec
    rpmdev-newspec
```
<!-- end_slide -->
Check SPEC files
================
<!-- new_line -->
<!-- pause -->
```bash +exec
   head -n 20 ~/rpmbuild/SPECS/local_repository.spec
```
