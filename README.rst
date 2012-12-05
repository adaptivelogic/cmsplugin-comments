===================
cmsplugin-comments
===================

A django-cms plugin for adding comments

Dependencies
------------
* captcha

Installation
------------

::

    pip install cmsplugin-comments

settings.py::

    INSTALLED_APPS = (
        ...
        'cmsplugin_comments',
        ...
    )

urls.py::

    urlpatterns = patterns('',
        ...
        url(r'^comments/', include('django.contrib.comments.urls')),
        ...
    )

Enable captcha
--------------

settings.py::

    INSTALLED_APPS = (
        ...
        'cmsplugin_comments',
        ...
    )

    COMMENTS_APP = 'cmsplugin_comments'

urls.py::

     urlpatterns = patterns('',
        ...
        url(r'^comments/', include('captcha.urls')),
        ...
    )


Enable emailing of new messages to admins
-----------------------------------------

settings.py::

    EMAIL_HOST=
    EMAIL_PORT=
    EMAIL_HOST_USER='my@email.com'
    EMAIL_HOST_PASSWORD='xxx'
    EMAIL_USE_TLS=True


    touch {project-home}/templates/comments/comment_notification_email.txt

finally::

    manage.py syncdb
    manage.py migrate
