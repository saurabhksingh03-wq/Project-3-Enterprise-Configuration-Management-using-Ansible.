                              +----------------------+
                              |   Developer Laptop   |
                              +----------+-----------+
                                         |
                                         | Git Push / SSH
                                         |
                                         v
                           +-----------------------------+
                           |      Ansible Master         |
                           | (Control Node / RHEL EC2)  |
                           +-------------+---------------+
                                         |
                     SSH (Port 22) using id_ed25519 Key
                     -----------------------------------
                          |                         |
                          |                         |
                          v                         v
                +----------------+        +----------------+
                |     Web01      |        |     Web02      |
                | Managed Node   |        | Managed Node   |
                | Apache Server  |        | Apache Server  |
                +----------------+        +----------------+
