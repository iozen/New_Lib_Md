#git #fix #git_pull #force_push 


~~~bash
git push -f h master
~~~



```bash
git pull --rebase
git push
```

The full syntax is:

```bash
git pull --rebase origin main
git push origin main
```

[With Git 2.6+](https://stackoverflow.com/a/30209750/6309) (Sept. 2015), after having done (once)

```bash
git config --global pull.rebase true
git config --global rebase.autoStash true
```

