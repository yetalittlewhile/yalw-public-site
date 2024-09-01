## Overview

This is the source for the yetalittlewhile.com site. there are two published locations:

* [dev.yetalittlewhile.com](https://dev.yetalittlewhile.com/) which corresponds to the `dev.yetalittlewhile.com` branch
* [yetalittlewhile.com](https://yetalittlewhile.com/) which corresponds to the `main` branch


## How to make changes:

### local edits
* first run a httpd so you can preview your work. i run `python3 -m http.server` but any server will do.
* navigate to the server, e.g. at [localhost:8000/src/](http://localhost:8000/src/)
* change to the `dev.yetalittlewhile.com` branch: `git checkout -b dev.yetalittlewhile.com` and rebase `git rebase main`.
* modify files and preview locally.
* `git add` and `git commit` your work when appropriate. when you `git push` to the origin, a GCP Cloud Build job defined in [cloudbuild-dev.yaml](cloudbuild-dev.yaml) will very quickly publish to [dev.yetalittlewhile.com](https://dev.yetalittlewhile.com/) automatically. Preview and qualify the changes there. 

### Publish to prod

* merge your work back to `main`: `git checkout main`; `git merge dev.yetalittlewhile.com`
* preview using the local httpd as above.
* `git add` and `git commit` and `git push` 
* manually publish: `cd src; gsutil -m rsync -r -d  .   gs://yetalittlewhile.com/`
* test [yetalittlewhile.com](https://yetalittlewhile.com/) and enjoy a rosie for your mystic efforts.


## TODO

* TODO maybe consider having some composition so pages can use same layout
* TODO prevent commits directly to `main` and then publish on merges.


