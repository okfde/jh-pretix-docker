FROM pretix/standalone

USER pretixuser

RUN cd /pretix/src/pretix/locale/de_Informal/LC_MESSAGES

COPY ./po/django.po ./pretix/src/pretic/locale/de_Informal/LC_MESSAGES
COPY ./po/djangojs.po ./pretix/src/pretic/locale/de_Informal/LC_MESSAGES

RUN cd /pretix/src && make production
