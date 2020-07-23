# heroku-jupyter

Use this application to deploy [Jupyter Notebook](https://jupyter.org/) to heroku or CloudFoundry. If a postres database is available, [pgcontents](https://github.com/quantopian/pgcontents) is used as notebook storage.

## Quick start

After deploying this application, jupyter is password protected with a random password. Set the environment variable `JUPYTER_NOTEBOOK_PASSWORD` and restart you app.

If you want to customize your app, easiest is to fork this repository.

## Installation instructions

### heroku - automatic deployment

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://dashboard.heroku.com/new?button-url=https%3A%2F%2Felements.heroku.com%2F&template=https%3A%2F%2Fgithub.com%2Fitq5%2Fheroku-jupyter)

If you forked this repository, you can link it to your heroku app afterwards.

### heroku - manual deployment

Push this repository to your app or fork this repository on github and link your 
repository to your heroku app.

Use the [heroku-buildpack-conda](https://github.com/itq5/heroku-buildpack-conda):
```
$ heroku buildpacks:set https://github.com/itq5/heroku-buildpack-conda.git -a <your_app>
```

To protect your notebooks a random password is used until you set the environment variable `JUPYTER_NOTEBOOK_PASSWORD`:
```
$ heroku config:set JUPYTER_NOTEBOOK_PASSWORD=<your_passwd> -a <your_app>
```

### CloudFoundry

- Clone this repository
- Create a postgres database with name `jupyter-db`
- Deploy using `cf push`
