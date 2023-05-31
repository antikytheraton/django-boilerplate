FROM python:3.9

ADD ./starter /srv/starter

ADD ./config/requirements.txt /srv/starter
RUN pip3 install -r /srv/starter/requirements.txt

ADD ./config/start.sh /
ADD ./config/django-uwsgi.ini /etc/uwsgi/django-uwsgi.ini
ADD ./config/database-check.py /srv/config/database-check.py

RUN adduser --no-create-home --disabled-login --group --system django
RUN chown -R django:django /srv/starter

CMD [ "./start.sh" ]
