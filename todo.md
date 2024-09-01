

* TODO maybe consider having some composition so pages can use same layout
* TODO: remove this CI test push marker

## how to make changes:

* first run a httpd so you can preview your work. i run `python3 -m http.server` but server will do.
* navigate to the server, e.g. at [localhost:8000/src/](http://localhost:8000/src/)
* change files, preview, `git add` and then `git commit` your work
* to push to staging (fyi has public cdot access): 
  * `cd src; gsutil -m rsync -r -d  .   gs://dev.yetalittlewhile.com/`
  * check it out at [dev.yetalittlewhile.com](https://dev.yetalittlewhile.com) but keep in mind there might be cacheing because of cloudflare.
* to push to the broad cdot world of prod: 
  * `cd src; gsutil -m rsync -r -d  .   gs://yetalittlewhile.com/`
  * check it out at [yetalittlewhile.com](https://yetalittlewhile.com)
* enjoy your rosie

