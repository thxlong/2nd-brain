### Stash

You can create stash as patch file from one machine,then can share that patch file to another machines.

**Creating the stash as a patch**

```
$ git stash show "stash@{0}" -p > changes.patch
```

The “stash@{0}” is the ref of the stash.It will create patch file with latest stash. If you want different one use command `$ git stash list` to see your list of stashes and select which one you want to patch.

**Applying the patch**

Now transfer that stash to another machine and paste it into the root folder of your project. Then run this command

```
$ git apply changes.patch
```

If there is mistake and you want to reverse the change

```
$ git apply changes.patch --reverse
```