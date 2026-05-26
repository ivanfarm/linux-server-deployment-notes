# Apache Reverse Proxy Notes

## Purpose

This document explains the basic idea of using Apache as a reverse proxy for local backend services.

A reverse proxy is useful when an application runs locally on a server, but users need to access it through a public domain and HTTPS.

## Basic Idea

A backend service may run locally on a port such as:

http://localhost:3000

Instead of exposing this port directly to the internet, Apache can forward requests from a public route to the local service.

Example:

Public URL:

https://example.com/app

Local service:

http://localhost:3000/app

## Why Use a Reverse Proxy

A reverse proxy can help with:

- Keeping backend services behind the main web server
- Using one public domain for multiple services
- Handling HTTPS at Apache level
- Avoiding direct exposure of local ports
- Organizing services by routes
- Making deployment cleaner

## Example Apache Configuration Concept

Example route:

/totd

Example local backend:

http://localhost:3000/totd

Conceptual Apache directives:

ProxyPass /totd http://localhost:3000/totd  
ProxyPassReverse /totd http://localhost:3000/totd

This means that when a user opens the public route /totd, Apache forwards the request to the local backend service.

## Required Apache Modules

Common modules for reverse proxy setup:

- proxy
- proxy_http
- ssl
- rewrite

These modules allow Apache to forward HTTP requests, support HTTPS and handle route logic.

## Virtual Hosts

Apache virtual hosts allow one server to handle different domains or configurations.

A typical setup may include:

- Port 80 virtual host for HTTP
- Port 443 virtual host for HTTPS
- ServerName directive for the domain
- DocumentRoot for static files
- ProxyPass rules for backend routes

## Validation Commands

Useful commands for checking Apache configuration:

`apachectl -S`

Shows virtual host configuration.

`apachectl configtest`

Checks whether Apache configuration syntax is valid.

`systemctl status apache2`

Shows Apache service status.

`sudo systemctl reload apache2`

Reloads Apache after configuration changes.

## Common Problems

### Backend service is not running

If Apache forwards to localhost:3000 but the backend is stopped, the route will not work.

Check with:

`ss -tulpn`

or:

`curl http://localhost:3000`

### Apache module is missing

If proxy modules are not enabled, reverse proxy rules may not work.

### Wrong route

The public route and backend route must match the intended application path.

### HTTPS configuration issue

If HTTPS virtual host is not configured correctly, the service may work on HTTP but fail on HTTPS.

## Troubleshooting Checklist

- Is Apache running?
- Is the backend service running?
- Is the backend reachable from localhost?
- Are proxy modules enabled?
- Is the virtual host active?
- Is the domain pointing to the correct server?
- Does Apache configuration pass syntax test?
- Are firewall rules allowing the required ports?

## What I Practiced

- Understanding reverse proxy logic
- Reading Apache configuration
- Working with public routes and local services
- Validating server configuration
- Troubleshooting web service deployment
