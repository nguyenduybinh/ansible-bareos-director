# Role Name

------------

ansible-bareos-director

# Description
-------------
Sử dụng role cho việc cài đặt và cấu hình director node để quản lý tập trung việc backup và restore dữ liệu trên các client 

Role thực hiện cài đặt và cầu hình:
* bareos-dir: director daemon của bareos
* bareos-fd: file daemon để thực hiện backup dữ liệu trên  director node
* bareos-sd: local storage trên director node
* bareos-database-*sql: cài đặt database để lưu catalog của bareos( có thể sử dụng mysql hoặc postgresql)
* *sql-server: cài đặt sql server cho lưu trữ catalog

# Role Variables

--------------

Toàn bộ biến chương trình được lưu trong  defaults/main.yml

Có thể tùy biến các biến trong file này để phù hợp với các trường hợp cài đặt khác nhau

# Dependencies

------------

* Role viết cho cài đặt bareos trên Ubuntu 14.04
* Các cấu hình và cài đặt chạy với quyền root 

# Example Playbook

----------------

Phụ thuộc vào việc khai vào inventory trrong ansible:

Ví dụ test với VM Vagrant, host khai báo trong /etc/ansible/hosts, group [director]:

    - hosts: director
      remote_users: vagrant
      sudo: yes
      roles:
         - ansible-bareos-director


