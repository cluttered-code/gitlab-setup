# Gitlab CE Setup

## Hardware Requirements

**Recommended**
* **CPU:** 2 Cores
* **Memory:** 4 GB

[Gitlab CE hardware requirements by number of users](http://docs.gitlab.com/ce/install/requirements.html#hardware-requirements)

## Dependencies

```bash
sudo apt update
sudo apt install -y ca-certificates curl openssh-server postgresql-contrib postfix
```

**Postfix Options**
1. Internet Server
2. <EMAIL_URL> (example.com)

## Install Gitlab CE

```bash
cd /tmp
curl -sS https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | sudo bash
sudo apt-get install -y gitlab-ce
```

## Setup URL

```bash
sudo nano /etc/gitlab/gitlab.rb
```

**Change line:** external_url '<GITLAB_URL>' (http://gitlab.example.com)

```bash
sudo gitlab-ctl reconfigure
```

## First Time Login

1. **In Browser:** `http://<GITLAB_URL>`

2. Follow the prompts on page to set administrator password.

3. Login with the following credentials:
    * **Username:** root
    * **Password:** <PASSWORD_SET_IN_PROMPT>