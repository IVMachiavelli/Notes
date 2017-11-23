---
title: "Project"
draft: false
---

```bash
# Creating a new cystal project
crystal init app test

```
```bash
# In crystal shards are used for depenency management.
The shared.yml file contains.
- Name (name of the project)
- Version (Version of the project, crystal uses semver)
- Authors (Authors of the project)
- Licence (MIT by default) 
```
```bash
# Adding depenencies to shard.yml
depenencies:
    kemal:
        github: sdogruyol/kemal
        version: 0.14.1        

# Installing the dependencies        
# In the project directory run the command         
shards install
 ```



