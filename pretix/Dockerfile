FROM pretix/standalone

USER pretixuser

RUN cd /pretix/src/pretix/locale/de_Informal/LC_MESSAGES

COPY ./po/django.po .
COPY ./po/djangojs.po .

RUN cd /pretix/src && make production
