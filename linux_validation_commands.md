# Linux Validation Commands

## Purpose

This document contains useful Linux commands for checking server state, network configuration, services, firewall rules and deployment status.

These commands are useful when validating a Linux server setup or troubleshooting deployment problems.

## System Information

Show operating system information:

`lsb_release -a`

Show kernel and system information:

`uname -a`

Show uptime:

`uptime`

Show hostname:

`hostname`

Show current user:

`whoami`

## Network Information

Show IP addresses:

`ip addr`

Show active network connections and listening ports:

`ss -tulpn`

Test a local service:

`curl http://localhost:3000`

Test a public website:

`curl -I https://example.com`

## Apache Commands

Check Apache status:

`systemctl status apache2`

Check Apache virtual hosts:

`apachectl -S`

Check Apache configuration syntax:

`apachectl configtest`

Reload Apache:

`sudo systemctl reload apache2`

Restart Apache:

`sudo systemctl restart apache2`

## Firewall Commands

Check UFW status:

`sudo ufw status verbose`

Show numbered UFW rules:

`sudo ufw status numbered`

Allow SSH:

`sudo ufw allow ssh`

Allow HTTP:

`sudo ufw allow 80/tcp`

Allow HTTPS:

`sudo ufw allow 443/tcp`

## Process and Service Commands

List running processes:

`ps aux`

Find a process by name:

`ps aux | grep node`

Check service status:

`systemctl status service_name`

Show enabled services:

`systemctl list-unit-files --type=service`

## PM2 Commands

Show PM2 processes:

`pm2 status`

Show PM2 logs:

`pm2 logs`

Restart PM2 application:

`pm2 restart app_name`

Save PM2 process list:

`pm2 save`

## Docker Commands

Show running containers:

`docker ps`

Show all containers:

`docker ps -a`

Show Docker images:

`docker images`

Start Docker Compose services:

`docker compose up -d`

Stop Docker Compose services:

`docker compose down`

View container logs:

`docker logs container_name`

## File and Directory Commands

List files:

`ls -la`

Show current directory:

`pwd`

Read a file:

`cat file_name`

Follow a log file:

`tail -f file_name`

Find files:

`find . -name "file_name"`

## Git Commands

Check repository status:

`git status`

Show commit history:

`git log --oneline`

Add files:

`git add .`

Create commit:

`git commit -m "Update documentation"`

Push changes:

`git push`

## Troubleshooting Checklist

When something does not work, check:

1. Is the server reachable?
2. Is the service running?
3. Is the correct port open?
4. Is the firewall blocking traffic?
5. Is Apache configured correctly?
6. Is the backend reachable from localhost?
7. Are logs showing errors?
8. Was the service restarted after configuration changes?
9. Is the domain pointing to the correct server?
10. Does HTTPS work correctly?

## What I Practiced

- Checking Linux server state
- Validating services
- Reading logs
- Testing local and public routes
- Troubleshooting configuration problems
- Documenting useful command-line workflows
