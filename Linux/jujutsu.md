# jujutsu

## create the tracking

- use this for pre initialized git repo
```bash
jj git init --collate
```

- use this for new git initialized.
```bash
jj git init
```

### jj doesn't have branches but bookmarks

- tracking the main branch
```bash
jj bookmark track main@origin
```

- modify changes then we can declare the intent with similar to git commit message
```bash
jj describe "message"
```

- After modifing the resources we won't see the empty tag in jj log. then run this to changes.
```bash
jj status
```

- After all modification we need to commit the changes. the commit message will be there from describe but u can change it
```bash
jj commit
```

- Add this changes to a branch. we add bookmark to this part. fro change_id we need only first letter
```bash
jj bookmark create <bookmark name> -r <change_id>
```

- lets add a new branch from a main branch. This creates a new scratch buffer to make changes
```bash
jj new main
```

## Push to git
```bash
jj git push --bookmark <bookmark_name>
```

- delete a bookmark
```bash
jj bookmark delete <bookmark_name>
```

- delete a bookmark remote
```bash
jj git push --bookmark <bookmark_name>
```

- delete some modifications
```bash
jj abondon <change_id>
```

- Add remote 
```bash
jj git remote add <URL>
```

- List remotes
```bash
jj remote list
```

- Add remote fork
```bash
jj git remote add sudomateo <URL>
```

- fetch from remote defaults to origin
```bash
jj git fetch
```

- fetch from remote and fork
```bash
jj git fetch --all-remotes
```

- commit specific changes
```bash
jj split
```

```
