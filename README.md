# Django Registration App

## Intro
Submission for [Code Challenge 29 - Create a Simple Django App](https://pybit.es/codechallenge29.html) and reusable template to start your app from scratch with proper registration / login using the existing Django User model. It uses the [django-registration](https://django-registration.readthedocs.io/en/2.2/index.html) plugin, gmail and has all the necessary settings to deploy to Heroku. 

I will further detail here and write an article on it, stay tuned ...

### Required env variables

	export SECRET_KEY=xyz
	export DJANGO_ENV='local'  # app defaults to production

	export GMAIL_SMTP_USER=your_email_user
	export GMAIL_SMTP_PASSWORD=your_email_pw

	export DB_NAME='pybites_notifications'
	export DB_USER=a_user
	export DB_PW=xyz

Configuring the DB is even simpler in production using `dj_database_url`:
	
	[settings.py]

	if DJANGO_ENV == 'production':
		import dj_database_url
		db_from_env = dj_database_url.config(conn_max_age=500)
		DATABASES['default'].update(db_from_env)
