Role Vector
=========


Requirements
------------
Для установки роли отредактируйте 'requirements.yml'
 
````bash
  - name: vector_role
    src: git@github.com:kirill-karagodin/vector-role.git
    scm: git
    version: "[last version]"
````

Role Variables
--------------

**defaults/main.yaml** - изменяемые переменные (номер версии Vector)

**vars/main.yml** - директория установки ПО (по умолчанию /opt/vector\[номер версии]), при желании можно изменить

**tasks/download** - таски для получения дистрибутива (реализованно для CentOS7/8)

**tasks/install** - таски установки дистрибутива (реализованно для CentOS7/8) 

**tasks/configure.yml** - установка конфигурационного файла Vector

**tasks/main.yml** - сценарий установки Vector

Example Playbook
----------------
````bash
- name: Install Vector
  hosts: vector
  roles:
    - vector_role
````

License
-------

MIT

