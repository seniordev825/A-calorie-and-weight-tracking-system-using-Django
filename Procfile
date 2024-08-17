release: python mysite/manage.py migrate
web: gunicorn mysite.wsgi --chdir mysite --log-file -
