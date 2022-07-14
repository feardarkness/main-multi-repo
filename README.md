# Git Submodules

## Adding submodules to the project

Adding a new submodule:

```
# add a submodule in the folder child2-muti-repo (same name as the repo)
$ git submodule add git@github.com:feardarkness/child2-multi-repo.git

# add a submodule in the folder repos/events
$ git submodule add git@github.com:feardarkness/child2-multi-repo.git repos/events

```

In any case, the first time a submodule is added, a .gitmodules file is created.

## Pushing updates


### Option 1
In the main project (root folder), you can see the project modifications in the main project or in the submodules. Pushing modifications in the child modules requires that you are in the submodule folder and do a normal push

### Option 2


## Cloning the project

### Option 1

Cloning the main project
```
$ git clone git@github.com:feardarkness/main-repo.git
```

Then, run two commands to update/fetch the submodules:
```
$ git submodule init
$ git submodule update
```

### Option 2

Clone recursively

```
$ git clone --recurse-submodules git@github.com:feardarkness/main-repo.git
```

## Update project (including repositories) from the remote

### Option 1

Inside the submodule folder

```
$ git fetch
$ git merge origin/main
```

### Option 2

In the root folder of the main project
```
$ git submodule update --remote repos/events
```

## Setting the branch to pull from in the submodule


Setting the branch as *main* in the *repos/events* submodule.

```
$ git config -f .gitmodules submodule.repos/events.branch main
```

## Update all submodules

```
$ git submodule update --remote --merge
```