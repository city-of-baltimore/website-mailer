=============
websitemailer
=============


This will take a screenshot of a website and send it to a set of email addresses. This can be useful for dashboards, or other frequently updating websites that you want to have automatically delivered to your inbox.


Description
===========

To run the script, you can either use command line arguments, a configuration file, or a mix of both.

Installation
------------

To install, simply run::

    pip install websitemailer

Running
-------

To run it by command line, run::

    python -m websitemailer.main <cmd line args>

For example, this would take a screenshot of google.com and send it through smtp.gmail.com.::

    python -m websitemailer.main -s smtp.gmail.com -u <smtp username> -p <smtp password> -r http://www.google.com -t <to email address> -f <from email address>

You can also use a config file. Note that the 'message' section can also have HTML markup.::

    mailings: [{
       'to_emails': ['bcdotnotifications1@gmail.com'],
       'from_email': 'bcdotnotifications1@gmail.com',
       'subject': 'Test config subject1',
       'message': 'Test message1',
       'url': ['http://www.google.com']
       },
       {
       'to_emails': ['bcdotnotifications1@gmail.com'],
       'from_email': 'bcdotnotifications1@gmail.com',
       'subject': 'Test config subject2',
       'message': 'Test message2',
       'url': ['http://www.yahoo.com']
       }]

    smtp-server: 'test_server_config'
    smtp-username: 'test_username_config'
    smtp-password: 'test_password_config'
    chrome-bin: 'c:\testbin\config'

.. _pyscaffold-notes:

Testing
========

To run the test suite, run::

    python -m tox -e py39 -- --email_username bcdotnotifications@gmail.com --email_password eV^5d97% --smtp_server smtp.gmail.com --pop_server pop.gmail.com

Sometimes, Gmail will reject the login from the tests. In that case, you need to log into the account, and then go to https://accounts.google.com/DisplayUnlockCaptcha


Note
====

This project has been set up using PyScaffold 4.0.2. For details and usage
information on PyScaffold see https://pyscaffold.org/.
