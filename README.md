# Calorietracker

![Python Version](https://img.shields.io/badge/python-3.7-green)
[![Code Style](https://img.shields.io/badge/code%20style-autopep8-blue)][e7b2d569]
![Django Version](https://img.shields.io/badge/django-3.1-green)

[e7b2d569]: https://github.com/hhatto/autopep8 "autopep8"
![BTC](https://img.shields.io/badge/BTC-bc1q02p75kx3rqsdmuvnfdgqery9036qvggrcwdjnh-yellow)
![ETH](https://img.shields.io/badge/ETH-0x2231CE7FE3135d78c0624B3700462e9A3c7048e1-lightgrey)
![BCH](https://img.shields.io/badge/BCH-bitcoincash%3Aqrlgyuwt8myx9xz0d3je4gfgezy9xkj4sqf76rqtm0-green)

![CalorieTracker.io](brand_assets/molecule.svg)

An intelligent calorie and weight tracking assistant that learns with you.



### Installation & Requirements

   git and pip3 is assumed to be installed

    pip3 install pipenv
    git clone https://gitlab.com/balugitlab/calorietracker

    cd calorietracker
    pipenv sync    


### Getting Started & How to Run

  copy & rename the .env.example file to .env in the same dir and populate it with your data

  note: you probably don't need to fill in everything

  then run

    pipenv shell
    cd mysite
    ./manage.py runserver


### Known Bugs
2Fa Asking for a code even if disabled:

    2Fa will sometimes ask for a code on login after disabled which always will be invalid if cookies are not cleared





### Logging & Analytics

currently in use are Sentry, Plausible django-request and Motomo

https://plausible.io/sites

https://sentry.io/organizations/calorietrackerio/

https://calorietrackerio.matomo.cloud



### Gunicorn
WEB_CONCURRENCY is a synonym for workers or -w and is set as env var to 3
more info can be found at the below links

  - https://docs.gunicorn.org/en/stable/settings.html#worker-processes
  - https://devcenter.heroku.com/articles/optimizing-dyno-usage#concurrent-web-servers



### Enviroment

  Pipenv by default loads in a .env file automatically see .env.example for examples
  This needs to be mirrord on deployment on Dokku

  List of required ENV Vars:

  IMPORTANT All values are type string when read in by python

      DEBUG = True
      DJANGO_LOGLEVEL = INFO

      SECRET_KEY = $z^fbe7!k&aqq79n^9lnhb^0qn+5cym*vx1n2r8m05^5=0+$)7

      # Gmail SMTP
      EMAIL_HOST_PASSWORD = 43lak

      # Cloudinary:
      CLOUDINARY_API_KEY = jl354kj
      CLOUDINARY_API_SECRET = 534lk

      # Facebook:
      ZUCC_APP_ID = 244
      ZUCC_APP_SECRET = 8e5e8

      # Discord
      DISCORD_CLIENT_ID = 768
      DISCORD_SECRET = 4OTdwm2_betA
      DISCORD_KEY = 57a72a


      STRIPE_LIVE_MODE = False
      STRIPE_TEST_PUBLIC_KEY = pk_test_51
      STRIPE_TEST_SECRET_KEY = sk_test_51
      STRIPE_LIVE_PUBLIC_KEY = pk_live_51
      STRIPE_LIVE_SECRET_KEY = sk_live_51



### Dokku

**Postgres**

    dokku postgres:unlink djangodb calorietracker
    dokku postgres:destroy djangodb
    dokku postgres:create djangodb
    dokku postgres:link djangodb calorietracker

    To create superuser:

    dokku run calorietracker python mysite/manage.py createsuperuser

    To initialize test3 sampledata:

    dokku enter calorietracker
    cd mysite/
    python initializedata.py

    You will have to set test3 password via admin panel to login as test3.


### Backup

**Cronjobs**

    Hourly DB backups

    0 * * * * dokku postgres:export djangodb > djangodb.db


    Daily MFP Auto Sync
    0 0 * * * dokku run calorietracker python mysite/manage.py mfp_sync

    Daily Auto Renew letsencrypt certificates for all apps
    0 0 * * * dokku letsencrypt:auto-renew



### Package Documentation

**DateTimePicker**  

  - https://monim67.github.io/django-bootstrap-datepicker-plus/configure/
  - https://github.com/monim67/django-bootstrap-datepicker-plus


**django-activity-stream**

  - https://django-activity-stream.readthedocs.io/en/latest


**Django encrypted model fields**

 - https://github.com/georgemarshall/django-cryptography


**Pinax-referrals**


  There is some funny business going on with the 004 Migration file

  - https://github.com/pinax/pinax-referrals

**Allauth**

  - https://django-allauth.readthedocs.io/en/latest/index.html

**Django-friendship**

  - https://github.com/revsys/django-friendship/

**Sentry**

  - https://sentry.io/settings/calorietrackerio/usage/history/

**Django Debug Toolbar**

  - https://github.com/jazzband/django-debug-toolbar


**Django-request**

  - https://github.com/django-request/django-request

**Django-friendship**

  - https://github.com/revsys/django-friendship/

**django-cors-headers**

  - https://github.com/adamchainz/django-cors-headers

**python-memcached**

 - https://github.com/linsomniac/python-memcached

**django-cache-url**

 - https://github.com/epicserve/django-cache-url

**django-axes**

 - https://github.com/jazzband/django-axes


**django-multifactor**
  - https://pypi.org/project/django-multifactor/

**pinax-announcements**
 - https://github.com/pinax/pinax-announcements
**Pinax Messages**
 - https://github.com/pinax/pinax-messages



### Packages to Consider for further functionality or as alternatives

bio auth and more 2fa
https://pypi.org/project/django-mfa2/

alternative to axes
https://github.com/jazzband/django-defender


Attributions:
Icons made by <a href="http://www.freepik.com/" title="Freepik">Freepik</a> from <a href="https://www.flaticon.com/" title="Flaticon"> www.flaticon.com</a>
