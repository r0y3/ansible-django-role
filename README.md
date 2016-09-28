Role Name
=========

Ansible role for Django application deployment.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

```git_key_file_src``` - Local ssh key

```git_key_file``` - Remote ssh key location including the filename

```git_key_owner``` - The remote user who is going to own the ssh key.

```repo_url``` - Your django application repository.

```proj_path``` - Django application base directory.

```git_branch``` - The repository branch to be deployed.

```venv_path``` - virtualenv directory.

```reqs_path``` - Path to your requirements(.txt) file.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

    - hosts: staging
      become: True
      become_user: root
      vars:
         proj_name: projectzero
         locale: en_US.UTF-8

         user: "{{ ansible_ssh_user }}"
         venv_path: "{{ venv_home }}/{{ proj_name }}"
         venv_site_packages: "{{ venv_path }}/lib/python3.4/site-packages"
         repo_url: git@github.com:r0y3/projectzero.git
         proj_dirname: project
         proj_path: "{{ venv_path }}/{{ proj_dirname }}"
         reqs_path: "{{ proj_path }}/requirements/base.txt"
         python: "{{ venv_path }}/bin/python"
         manage: "{{ python }} {{ proj_path }}/manage.py"
         gunicorn_port: 9000
         fixtures: "categories.yaml tags.yaml"
         app_settings: "config.settings.staging"
         frontend_path: "{{ proj_path }}/projectzero-webapp"
         backend_path: "{{ proj_path }}/projectzero"

         git_key_file_src: /home/r0y3/.ssh/id_rsa
         git_key_file: /home/ubuntu/.ssh/id_rsa_r0y3.github
         git_key_owner: ubuntu

      roles:
         - { role: django }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
