# Git Hooks Samples

Some git-hook's samples.

### commit-msg 

```bash
#!/bin/sh

commit_msg=`cat $1`
check_flag=1

for commit in feat: dev: fix: chore: docs: style: perf: test:
do
    if [[ $commit_msg =~ ^"$commit".+ ]]; then
        check_flag=1
        break
    fi
    check_flag=2
done

if [[ $check_flag == "2" ]]
then
    echo "error: Commit-msg can not be empty and must begin with feat:/dev:/fix:/chore:/docs:/style:/perf:/test:"
    exit 1
fi
```
