# Linux Server Deployment Notes

A documentation-based project covering Linux server setup, Apache configuration, Docker services, PM2 process management, HTTPS and reverse proxy concepts.

## Project Overview

This repository documents practical Linux server administration and deployment tasks completed as part of academic and personal software engineering work.

The main goal of this project is to show understanding of how a Linux-based server environment can be configured, validated and documented.

The project focuses on:

- Linux server basics
- Apache web server configuration
- HTTPS setup concepts
- Reverse proxy configuration
- Docker-based services
- PM2 process management
- Command-line validation
- Troubleshooting and documentation

## Technologies and Tools

- Ubuntu Linux
- Apache HTTP Server
- Docker
- Docker Compose
- PM2
- Node.js
- SSH
- UFW firewall
- Bash
- Git
- Command-line tools

## Project Structure

linux-server-deployment-notes/

- README.md
- server_stack_overview.md
- apache_reverse_proxy_notes.md
- docker_and_pm2_notes.md
- linux_validation_commands.md
- LICENSE

## What This Project Demonstrates

- Understanding of Linux server environments
- Basic service deployment workflow
- Apache virtual host and reverse proxy concepts
- Running backend services behind a web server
- Using Docker for service isolation
- Managing Node.js processes with PM2
- Checking server state from the command line
- Writing clear technical documentation

## Example Deployment Concept

A typical setup can include:

1. A public domain connected to a Linux server.
2. Apache serving web content.
3. HTTPS enabled for secure access.
4. Backend services running locally.
5. Apache reverse proxy forwarding selected routes to local services.
6. PM2 keeping Node.js services alive.
7. Docker running isolated services such as databases or backend applications.
8. Validation commands used to check the configuration.

## Example Architecture

User browser  
→ HTTPS request  
→ Apache virtual host  
→ Static website or reverse proxy route  
→ Local backend service  
→ Optional database service in Docker

## What I Practiced

- Linux command-line usage
- Server configuration
- Apache setup
- Reverse proxy logic
- Docker basics
- PM2 process management
- Service validation
- Troubleshooting
- Technical documentation

## Possible Improvements

- Add example Apache virtual host files
- Add example Docker Compose configuration
- Add GitHub Actions documentation checks
- Add automated server validation script
- Add diagrams for deployment architecture
