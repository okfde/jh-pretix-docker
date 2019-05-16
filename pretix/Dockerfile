FROM pretix/standalone

COPY pretix/po/django.po .
COPY pretix/po/djangojs.po .

USER pretixuser

RUN cp django.po /pretix/src/pretix/locale/de_Informal/LC_MESSAGES/django.po
RUN cp djangojs.po /pretix/src/pretix/locale/de_Informal/LC_MESSAGES/djangojs.po

RUN cd /pretix/src && make production
