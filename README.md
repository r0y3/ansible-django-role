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

```app_repo_url``` - Your django application repository.

```app_proj_path``` - Django application base directory.

```app_git_branch``` - The repository branch to be deployed.

```app_venv_path``` - virtualenv directory.

```app_reqs_path``` - Path to your requirements(.txt) file.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
