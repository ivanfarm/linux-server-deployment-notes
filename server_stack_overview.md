# Server Stack Overview

## Purpose

This document describes a practical Linux server stack used for hosting web content and backend services.

The goal is to understand how different server components work together in a deployment environment.

## Main Components

### Linux Server

The Linux server is the base environment where all services are installed and configured.

Typical responsibilities:

- Running system services
- Managing users and permissions
- Hosting web applications
- Providing network access
- Running background processes
- Storing logs and configuration files

### Apache Web Server

Apache is used as the main web server.

Possible responsibilities:

- Serving static web pages
- Handling HTTP and HTTPS traffic
- Managing virtual hosts
- Acting as a reverse proxy
- Forwarding requests to backend services

### HTTPS

HTTPS is used to secure communication between the user and the server.

Purpose:

- Encrypt traffic
- Protect user data
- Improve trust and browser compatibility
- Support secure deployment practices

### Backend Services

Backend services can run locally on different ports.

Examples:

- Node.js application on localhost
- Python web service on localhost
- API server behind Apache
- Database-connected backend service

### Reverse Proxy

A reverse proxy allows Apache to forward requests from public URLs to local services.

Example:

Public route:

/totd

Local backend:

http://localhost:3000/totd

This allows users to access the service through the main domain while the backend remains local.

### Docker

Docker is used to run isolated services.

Possible use cases:

- Running a database
- Running a backend application
- Creating reproducible development environments
- Separating application dependencies

### PM2

PM2 is used to manage Node.js processes.

Main benefits:

- Keeps Node.js applications running
- Restarts applications after failure
- Shows process status
- Supports log viewing
- Can run services in the background

## Typical Request Flow

1. User opens a website in the browser.
2. Request reaches the Linux server.
3. Apache receives the request.
4. Apache serves static content or forwards the request.
5. Backend service processes the request.
6. Response is returned through Apache to the user.

## Why This Stack Is Useful

This stack is useful because it combines several real-world deployment concepts:

- Web server configuration
- Backend service hosting
- Secure access through HTTPS
- Process management
- Service isolation
- Command-line troubleshooting

## Skills Practiced

- Understanding server architecture
- Working with Linux services
- Reading and editing configuration files
- Checking ports and running processes
- Debugging deployment problems
- Documenting technical systems
