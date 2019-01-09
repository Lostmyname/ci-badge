# Heroku CI Badges

Get a Heroku CI badge for your repo's README file.

__NOTE: This project is a fork of https://github.com/gregsadetsky/heroku-ci-badge__

![example badge](badges/succeeded.svg) ![example badge](badges/failed.svg)

## Troubleshooting

If you're seeing...

![error badge](badges/error.svg)

... instead of a pass/fail mark, it means that the heroku-ci-badge app could not retrieve the build status.
- Check that you've set the `HEROKU_AUTH_TOKEN` environment variable on your app
- Check that your auth token is valid by running `heroku authorizations` . Note that token _IDs_ (shown in the list) and the token _values_ are not the same. Do you see the "heroku-ci-badge" token generated previously? If you run `heroku authorizations:info {token id}` is the `Token: {token value}` value the same as the one you set as the `HEROKU_AUTH_TOKEN` environment variable?
- Check that you've set the `PIPELINE_ID` environment variable on your app
- Check that the `PIPELINE_ID` value is valid by checking the pipeline URL `https://dashboard.heroku.com/pipelines/{pipeline ID}`
- Check the app's log outputs for errors: `heroku log -a {deployed app name}`

If you're seeing...

![image not found](badges/chrome-noimage.png)

... it means that:
- the image URL might be wrong (check the public URL to your deployed app, and that you're referencing `/last.svg`)
- your heroku-ci-badge app might be sleeping if you're using a Free Dyno. See [here](https://devcenter.heroku.com/articles/free-dyno-hours#dyno-sleeping): "If an app has a Free web dyno, and that dyno receives no web traffic in a 30-minute period, it will sleep". Upgrade the dyno type to `hobby` (7$/month) to remedy.


## Disclaimers

- This software is provided as is.
- This project has no affiliation with Heroku.
