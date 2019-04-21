---
layout: default
title: "My git config file"
---

# My git config file

```
[pull]
	rebase = true
[core]
	autocrlf = false
	longpaths = true

[alias]
	st = status
	lg = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)'
	dob = "!f() {\
			git checkout master;\
			git branch -vv | grep ': gone]' | awk '{print $1}' | xargs git branch -d;\
			}; f"
[fetch]
	prune = true
```





