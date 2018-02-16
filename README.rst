Ansible Role Supervisor
#######################

|Build Status| |Ansible Galaxy| |GitHub issues| |Average time to resolve an issue| |Percentage of issues still open| |GitHub license|

:Version: 0.1.1
:Web: https://github.com/hadenlabs/ansible-role-supervisor
:Download: http://github.com/hadenlabs/ansible-role-supervisor
:Source: http://github.com/hadenlabs/ansible-role-supervisor
:Keywords: ansible-role-supervisor

.. contents:: Table of Contents:
    :local:

Ansible Galaxy role for `Supervisor`_.

Requirements:
=============

List of applications:

- `Python 3.6.1`_
- `Docker`_
- `Docker Compose`_

Install
=======

Install it with the following command:

.. code-block:: bash

    $ ansible-galaxy install hadenlabs.supervisor

Role Variables
==============

The default role variables in ``defaults/main.yml`` are:

.. code-block:: yaml

    supervisor_user: {{user}}

    # defaults file for supervisor
    supervisor_apps:
      - program: name
        application_path: /home/user/project/src
        application_environment: {{ deployment_file_load_virtualenvwrapper }}
        execution: celery -A {{ app_name }} worker --loglevel=info

    supervisor_programs:
      - program: name
        command: 'command'
        user: "user"
        directory: "directory"
        numprocs: 1
        instalautostart: true
        autorestart: true
        startsecs: 10
        priority: 990
        disabled_program: name program to disabled


Dependencies
============

None

Example Playbook
================

See the `examples <./examples/>`__ directory.

To run this playbook with default settings, create a basic playbook like
this:

.. code:: yaml

    - hosts: servers
        roles:
        - hadenlabs.supervisor

License
=======

MIT

Changelog
=========

Please see `CHANGELOG`_ for more information what
has changed recently.

Contributing
============

Please see `CONTRIBUTING`_ for details.

Credits
=======

-  `author`_
-  `contributors`_

Made with :heart: :coffee: and :pizza: by `author`_ and `company`_.

.. Badges:

.. |Build Status| image:: https://travis-ci.org/hadenlabs/ansible-role-supervisor.svg
   :target: https://travis-ci.org/hadenlabs/ansible-role-supervisor
.. |Ansible Galaxy| image:: https://img.shields.io/badge/galaxy-hadenlabs.supervisor-blue.svg
   :target: https://galaxy.ansible.com/hadenlabs/ansible-role-supervisor/
.. |GitHub issues| image:: https://img.shields.io/github/issues/hadenlabs/ansible-role-supervisor.svg
   :target: https://github.com/hadenlabs/ansible-role-supervisor/issues
.. |Average time to resolve an issue| image:: http://isitmaintained.com/badge/resolution/hadenlabs/ansible-role-supervisor.svg
   :target: http://isitmaintained.com/project/hadenlabs/ansible-role-supervisor
.. |Percentage of issues still open| image:: http://isitmaintained.com/badge/open/hadenlabs/ansible-role-supervisor.svg
   :target: http://isitmaintained.com/project/hadenlabs/ansible-role-supervisor
.. |GitHub license| image:: https://img.shields.io/github/license/mashape/apistatus.svg?style=flat-square
   :target: LICENSE

.. Links
.. _`changelog`: CHANGELOG.rst
.. _`contributors`: AUTHORS
.. _`contributing`: CONTRIBUTING.rst

.. _`company`: https://github.com/hadenlabs
.. _`author`: https://github.com/luismayta

.. dependences
.. _Supervisor: https://www.supervisor.com
.. _Python: https://www.python.org
.. _Python 3.6.1: https://www.python.org/downloads/release/python-361
.. _Docker: https://www.docker.com/
.. _Docker Compose: https://docs.docker.com/compose/