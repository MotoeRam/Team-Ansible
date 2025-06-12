
🔍 Check Connectivity

ansible all -i inventory.ini -m ping

Checks if Ansible can connect to all nodes.

📂 Copy Files

ansible all -i inventory.ini -m copy -a "src=/path/to/local/file dest=/remote/path/file"

Copies a file from the control node to all managed nodes.

🔧 Run Shell Commands

ansible all -i inventory.ini -m shell -a "uptime"

Executes the given shell command on remote hosts.

📦 Install a Package

ansible all -i inventory.ini -m package -a "name=htop state=present"

Installs a package using the system's package manager (YUM, APT, etc.).

❌ Remove a Package

ansible all -i inventory.ini -m package -a "name=htop state=absent"

Removes a package.

🔁 Reboot a Machine

ansible all -i inventory.ini -m reboot

Reboots the target machines.

📁 Create a Directory

ansible all -i inventory.ini -m file -a "path=/opt/mydir state=directory mode=0755"

Creates a directory with specified permissions.

🗑️ Delete a File or Directory

ansible all -i inventory.ini -m file -a "path=/tmp/testfile state=absent"

Deletes a file or directory.

🧑 Add a User

ansible all -i inventory.ini -m user -a "name=devops state=present"

Creates a new user.

🔐 Manage Services

Start a Service

ansible all -i inventory.ini -m service -a "name=nginx state=started"

Restart a Service

ansible all -i inventory.ini -m service -a "name=nginx state=restarted"

Stop a Service

ansible all -i inventory.ini -m service -a "name=nginx state=stopped"

🧪 Run Python One-Liner

ansible all -i inventory.ini -m command -a "python3 -c 'print(42)'"

Runs a quick Python script remotely.

💾 Gather Facts

ansible all -i inventory.ini -m setup

Collects system information (RAM, IP, CPU, OS, etc.) from remote hosts.

📚 References

Docs: https://docs.ansible.com/ansible/latest/cli/ansible.html

Module Index: https://docs.ansible.com/ansible/latest/collections/index_module.html

Use --limit to target specific hosts:

ansible all -i inventory.ini -m ping --limit webservers

Use --become for privilege escalation:

ansible all -i inventory.ini -m apt -a "name=nginx state=present" --become

Happy Automating! 🚀
