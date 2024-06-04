---
layout: post
title: CSAIL MIT 01 - Shell and Shell Scripting
---

Shell is what we basically use to interact with the system/kernel at low level.

Shell scripting is basically a script that we give to the system and system will perform all the tasks/commands in it one-by-one
its very useful when doing repetative tasks and to automate some executions.

### Basic format
```
#!/bin/bash
ls -la
echo "hello" > File1.txt
```

### Variables
```
#!/bin/bash
TEST="this is a sample string"
echo $TEST
```

### Taking arguments from user
```
#!/bin/bash
mkdir -p "$1"
```
### Execute commands based on previous commands exit code
```
#!/bin/bash
systemctl status $1 > /dev/null

if [ $? = 0 ]
then
        echo "previous commands output was true"
else
        echo "previous commands output was false"
fi
```

### Script to find specified file and perform specified action/command on it
```
#!/bin/bash
find . -iname $1 -exec $2 {} \;
```