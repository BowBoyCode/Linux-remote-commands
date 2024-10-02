# Description
In Linux, the `p` in `scp` stands for **"protocol"** or **"secure"**, as `scp` stands for **Secure Copy Protocol**.
It is a command used to securely transfer files between computers over a network, typically using the SSH (Secure Shell) protocol. 
The `scp` command allows for encrypted file transfers, ensuring that the data is securely copied from one system to another.

# Installation notes
#### Copying from Local to Remote
scp /path/to/local/file username@remote_host:/path/to/remote/directory
scp myfile.txt user@192.168.1.100:/home/user/

### Copying from Remote to Local
scp username@remote_host:/path/to/remote/file /path/to/local/directory
scp user@192.168.1.100:/home/user/myfile.txt /home/localuser/

### Copying Between Two Remote Hosts
scp username1@remote_host1:/path/to/file username2@remote_host2:/path/to/directory

### Common Options
##### -r: Copy directories recursively.
##### -P <port>: Specify a custom port if the SSH server is running on a non-default port.
##### -i <identity_file>: Use a specific SSH private key.

### Example: Copying a Directory Recursively
scp -r /path/to/local_directory user@remote_host:/path/to/remote_directory

In Linux, "remote commands" generally refer to those that allow you to interact with remote systems. Below is a list of commonly used remote commands:

### 1. **SSH (Secure Shell)**
   - Used to securely connect to a remote machine.
   - Syntax: 
     ```bash
     ssh user@remote_host
     ```

### 2. **SCP (Secure Copy Protocol)**
   - Copies files securely between local and remote machines.
   - Syntax:
     ```bash
     scp file.txt user@remote_host:/path/to/destination
     ```

### 3. **rsync**
   - Synchronizes files and directories between local and remote systems with support for incremental updates.
   - Syntax:
     ```bash
     rsync -avz /local/dir user@remote_host:/remote/dir
     ```

### 4. **SFTP (Secure File Transfer Protocol)**
   - Allows secure file transfer over SSH.
   - Syntax:
     ```bash
     sftp user@remote_host
     ```

### 5. **FTP (File Transfer Protocol)**
   - Transfers files between local and remote servers.
   - Syntax:
     ```bash
     ftp remote_host
     ```

### 6. **RDP (Remote Desktop Protocol)**
   - Provides a graphical interface to connect to another computer over a network.
   - Syntax (using a client like `rdesktop`):
     ```bash
     rdesktop remote_host
     ```

### 7. **VNC (Virtual Network Computing)**
   - Allows remote graphical control of another computer.
   - Syntax:
     ```bash
     vncviewer remote_host:port
     ```

### 8. **telnet**
   - An older, unsecured protocol for remote communication.
   - Syntax:
     ```bash
     telnet remote_host
     ```

### 9. **netcat (nc)**
   - Used to establish network connections and send/receive data.
   - Syntax:
     ```bash
     nc remote_host port
     ```

### 10. **curl**
   - Transfers data to/from a remote server.
   - Syntax:
     ```bash
     curl http://remote_host/file.txt
     ```

### 11. **wget**
   - Retrieves files from a remote server.
   - Syntax:
     ```bash
     wget http://remote_host/file.txt
     ```

### 12. **Ansible**
   - A tool for automating remote commands across multiple systems.
   - Syntax:
     ```bash
     ansible -i inventory all -m command -a "uname -a"
     ```

### 13. **mosh (Mobile Shell)**
   - A remote shell with better support for intermittent connectivity.
   - Syntax:
     ```bash
     mosh user@remote_host
     ```

### 14. **rdist**
   - A command to maintain identical copies of files across multiple systems.
   - Syntax:
     ```bash
     rdist -P ssh /path/to/local_file user@remote_host:/path/to/remote_directory
     ```

### 15. **screen (with SSH)**
   - Allows you to run programs remotely and resume sessions.
   - Syntax:
     ```bash
     screen ssh user@remote_host
     ```

### 16. **tmux (with SSH)**
   - Terminal multiplexer that allows you to keep remote sessions running.
   - Syntax:
     ```bash
     tmux new-session ssh user@remote_host
     ```

### 17. **OpenVPN**
   - Establishes a secure VPN connection to a remote host.
   - Syntax:
     ```bash
     openvpn --config client.ovpn
     ```

### 18. **WireGuard**
   - A modern VPN tool to connect to a remote network securely.
   - Syntax:
     ```bash
     wg-quick up /path/to/wg0.conf
     ```

### 19. **remote execution via `at`**
   - Executes commands at a specified time on a remote machine.
   - Syntax:
     ```bash
     ssh user@remote_host 'echo "command" | at now + 1 minute'
     ```

### 20. **remote execution via `cron`**
   - Automates scheduled tasks on a remote machine.
   - Syntax:
     ```bash
     ssh user@remote_host 'echo "* * * * * command" | crontab -'
     ```

These tools allow you to access, transfer files, manage, or control remote systems in different ways. Let me know if you'd like more details on any of these!
