# Ansible Modules

1. **Command Module**:
    - Executes binary commands without using a shell, making it more secure.
    - **Example**: `ansible all -m ping`, `ansible all -a "uptime"`

2. **Shell Module**:
    - Executes commands through a shell, allowing the use of shell features like `&&`, `|`, etc.
    - **Example**: `ansible web -m shell -a "cat /etc/passwd && pwd"`

3. **File Module**:
    - Manages files and directories (create, delete, modify).
    - **Example**: `ansible web -m file -a "path=project.txt state=touch"`

4. **Copy Module**:
    - Copies files between the control node and remote nodes.
    - **Example**: `ansible web -m copy -a "src=/etc/hosts dest=/home/ansible"`

5. **Fetch Module**:
    - Downloads files from remote nodes to the control machine.
    - **Example**: `ansible web -m fetch -a "src=/home/ansible/file.txt dest=/tmp/file.txt"`

6. **Yum Module**:
    - Installs or manages packages on remote nodes (for systems using Yum).
    - **Example**: `ansible all -m yum -a "name=nginx state=present" --become`

7. **Service Module**:
    - Manages services on remote nodes (start, stop, restart).
    - **Example**: `ansible all -m service -a "name=nginx state=restarted" --become -K`

8. **User Module**:
    - Manages user accounts.
    - **Example**: `ansible db -m user -a "name=mark password=wiyiMQbLhCRUY shell=/bin/bash" -b`

9. **Setup Module**:
    - Gathers facts about remote hosts (system information).
    - **Example**: `ansible db -m setup`

10. **Debug Module**:
    - Displays messages or variable values for debugging purposes.
    - **Example**: `ansible all -m debug -a "var='inventory_hostname'"`
