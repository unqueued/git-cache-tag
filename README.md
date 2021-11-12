# git-cache-tag

It can be really useful because you may want a complete snapshot of stuff
that is not normally tracked by git.

Be careful because that this may include your secrets. However, if you are using a tool like (git-crypt)[https://github.com/AGWA/git-crypt] that uses a smudge filter, then this won't decrypt them when it adds it to the cache.

If you want to commit stuff like node_modules without bloating your repo, the commits that this script creates are leaves and can be deleted later without having to rewrite history.

Very helpful for node_modules folder because it may not be re-created the same by npm install.

To restore just something like node_modules from a cache, do:

```bash
  git checkout snapshot/[snapshot_name] -- node_modules
```

You probably want to keep your caches local. But you could also push a cache and it could save you a lot of time in your CI to have it check out a cached snapshot.
