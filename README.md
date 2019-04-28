# Swagger Editor and UI on Local Environment

**Don't push api documents to you remote repositories.**

## Initialization

1. Prevent you from pushing to your remote repositories accidently

Should write down the following scripts on `.git/hooks/pre-push`.
And have to prohibit you from push api documents to your remote repositories.

```
#!/bin/bash

while read local_ref local_sha1 remote_ref remote_sha1
do
    echo -e "\033[01;31mDo not push to remote repositories.\033[00m"
    exit 1
done
```

2. Fetch submodules about swagger-editor.

```
git submodule update --init
```
