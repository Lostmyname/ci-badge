# Heroku CI Badges

Get a Heroku CI badge for your repo's README file.

![example badge](badges/succeeded.svg) ![example badge](badges/failed.svg)



## Adding a new App

Updating the app's code once it's deployed is not as easy as doing the initial deployment (i.e., it's not a single click). Based on the instructions [here](https://f-a.nz/dev/update-deploy-to-heroku-app/), here are the steps to update deployed `heroku-ci-badge` apps:

    # Instructions for the first update only (see below for further updates)
    # Add an app to the heroku pipeline: https://dashboard.heroku.com/pipelines/9baf2a12-d803-4e75-a6a0-6efd83055ca6
    
    heroku git:remote -a {deployed app name}
    git pull origin master
    git push heroku master

For further updates:

    # change to the app
    heroku git:remote -a {deployed app name}
    git pull origin master
    git push heroku master

## Disclaimers

- This software is provided as is.
- This project has no affiliation with Heroku.
