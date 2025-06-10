# 🛡️ SSH Tutorial for Beginners

SSH (Secure Shell) is a protocol used to securely access and manage remote computers over a network. It provides encrypted communication for login, file transfers, and command execution.

---

## 📦 Installing OpenSSH

### 🖥️ On the Server (Linux)

To allow incoming SSH connections, install the **OpenSSH Server**:

#### Debian/Ubuntu

```bash
sudo apt update
sudo apt install openssh-server
```

#### Fedora

```bash
sudo dnf install openssh-server
sudo systemctl enable --now sshd
```

#### Arch Linux

```bash
sudo pacman -S openssh
sudo systemctl enable --now sshd
```

### 🔍 Check SSH Status

```bash
sudo systemctl status ssh
```

It should say `active (running)`.

---

## 🚀 Connecting via SSH (Client)

Use this command from your **local machine**:

```bash
ssh username@host
```

**Example:**

```bash
ssh alice@192.168.1.10
```

You’ll be prompted to enter the remote password.

---

## 🔐 SSH Key-Based Login (Optional but Recommended)

### 1. Generate a Key Pair (on client)

```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

Accept defaults (`~/.ssh/id_rsa`) by pressing Enter.

### 2. Copy Public Key to Server

```bash
ssh-copy-id alice@192.168.1.10
```

You’ll be prompted for the server password **one last time**. After that, login won’t require a password.

---

## 📁 Secure File Transfer with SCP

### From local to remote:

```bash
scp file.txt user@remote_host:/remote/path/
```

**Example:**

```bash
scp myfile.txt alice@192.168.1.10:/home/alice/
```

### From remote to local:

```bash
scp user@remote_host:/remote/file.txt /local/path/
```

---

## 🔁 Recursively Copy Folders

```bash
scp -r myfolder user@host:/remote/path/
```

---

## 🔧 Port Forwarding

Tunnel remote services to your local machine:

```bash
ssh -L 8080:localhost:80 user@host
```

Now `localhost:8080` on your machine maps to `localhost:80` on the remote server.

---

## 🗂️ SSH Config File for Easy Connections

Edit or create `~/.ssh/config`:

```ini
Host myserver
  HostName 192.168.1.10
  User alice
  IdentityFile ~/.ssh/id_rsa
  Port 22
```

Then simply run:

```bash
ssh myserver
```

---

## 📋 Summary of Basic SSH Commands

| Task                    | Command                                        |
| ----------------------- | ---------------------------------------------- |
| Connect to server       | `ssh user@host`                                |
| Copy file to server     | `scp file.txt user@host:/path/`                |
| Copy file from server   | `scp user@host:/file.txt .`                    |
| Copy folder recursively | `scp -r folder user@host:/path/`               |
| Generate SSH key pair   | `ssh-keygen`                                   |
| Copy key to server      | `ssh-copy-id user@host`                        |
| Enable port forwarding  | `ssh -L local_port:host:remote_port user@host` |
| Configure easy login    | Edit `~/.ssh/config`                           |

---

## 🔐 Security Tips

* Disable root login: Edit `/etc/ssh/sshd_config` → `PermitRootLogin no`
* Change default port: `Port 2222` (or similar) in `/etc/ssh/sshd_config`
* Use `ufw` or `firewalld` to limit SSH access
* Install `fail2ban` to block brute-force attacks

---

## 🧪 Testing SSH Connection

1. Make sure the server is **powered on** and connected to the **network**.
2. Use `ping <IP>` to verify connectivity.
3. Try connecting with:

```bash
ssh user@IP_ADDRESS
```

---

## 🔄 Restart SSH Service (if needed)

```bash
sudo systemctl restart ssh
```


