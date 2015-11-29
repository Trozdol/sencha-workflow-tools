# sencha-workflow-tools
Some misc things to make Sencha and Cordova projects work a little better in Git.

### Sencha Touch, Cordova, Git and Teams

Working on a Sencha Touch and Cordova/Phonegap project can be tricky enough. Working on one in a team of developers can be more of a job.

After a couple of years of difficult merge conflicts, generated files and out of repo manual merges. I believe I have found a workflow specifically to deal with common issues.

### Branch Workflow

So far this system has worked will with minimal issues if any. 

```
master ____________________ tag-v0.0.1 ___ tag-v0.0.2 _ _ . .
      \_ build ____________/______________/_________ _ _ . .
            \_ development ______/______________ _ _ . .
                    \_ working-branch-01 _/

```


### What to ignore...

This seemed straight forward... until I started thinking about it. For a while I used what others talked about in forums or blogs for which parts of a Sencha/Cordova project to ignore. This seemed to lead to issues eventually. I could never find a clear answer so I asked myself

> What changes do I need to create a Cordova build? 

...Or...

> What does someone else need if they clone a repo right now?

The tricky part is where generated vs edited files overlap. Here's what I've chosen to ignore specifically for the Sencha Touch part of a repo.

The below are ignored becuase any other developer can recreate these with Sencha CMD using one or more `sencha` commands.

```bash

# ========================================
# SENCHA
# ----------------------------------------
.sencha_backup/
archive/
build/
resources/sass/.sass-cache/
resources/css/app.css
bootstrap.js
bootstrap.json

```




### Post Merge Git Hooks



`post-merge`: 

This git hook will help with the `.gitignore` file when working in teams

```    
    my-project/.git/hooks/post-merge
    
    cd my-project/.git/hooks/ && chmod +x
```

