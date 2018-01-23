# Setting up Jekyll on the AIL Server

## Introduction

## Installing RVM

## Cloning Jekyll

## Access Permissions
An access control list (ACL) must be created for the Jekyll folder, all its contents, and anything that is added/copied into it (inheritance).
```
chmod +a "group:examplegroup allow list,add_file,search,add_subdirectory,delete_child,readattr,writeattr,readextattr,writeextattr,readsecurity,file_inherit,directory_inherit" /path/to/folder
```
