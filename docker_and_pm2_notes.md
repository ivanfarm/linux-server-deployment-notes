# Docker and PM2 Notes

## Purpose

This document explains how Docker and PM2 can be used in a Linux server environment.

Docker is useful for running isolated services. PM2 is useful for managing Node.js applications as background processes.

## Docker

Docker allows applications and services to run in containers.

A container includes the application and its dependencies, which makes the environment easier to reproduce.

## Why Use Docker

Docker can help with:

- Running services in isolated environments
- Managing dependencies
- Running databases locally
- Testing deployment setups
- Keeping services separated
- Reproducing the same setup on another machine

## Docker Compose

Docker Compose allows multiple services to be defined in one configuration file.

Example services:

- Backend application
- PostgreSQL database
- Admin tool
- Cache service

A typical Docker Compose setup may include:

- Service name
- Image
- Ports
- Environment variables
- Volumes
- Networks

## Useful Docker Commands

List running containers:

`docker ps`

List all containers:

`docker ps -a`

Start services:

`docker compose up -d`

Stop services:

`docker compose down`

View logs:

`docker logs container_name`

Check images:

`docker images`

## PostgreSQL in Docker

PostgreSQL can be run as a Docker container for development and testing.

Common configuration values:

- Database name
- Username
- Password
- Port mapping
- Volume for persistent data

## PM2

PM2 is a process manager often used for Node.js applications.

It helps keep applications running in the background.

## Why Use PM2

PM2 can help with:

- Starting Node.js applications
- Restarting applications after crashes
- Viewing process status
- Viewing logs
- Running applications after server restart
- Managing multiple services

## Useful PM2 Commands

Start an application:

`pm2 start app.js --name my-app`

Show running processes:

`pm2 status`

View logs:

`pm2 logs`

Restart an application:

`pm2 restart my-app`

Stop an application:

`pm2 stop my-app`

Save current process list:

`pm2 save`

## Docker vs PM2

Docker and PM2 solve different problems.

Docker focuses on containerization and isolated environments.

PM2 focuses on managing Node.js processes.

They can be used together, but they can also be used separately depending on the deployment structure.

## Example Deployment Idea

A simple deployment may use:

- Apache as the public web server
- PM2 for a Node.js backend service
- Docker for PostgreSQL
- Reverse proxy from Apache to the Node.js service

## What I Practiced

- Understanding container-based services
- Managing application processes
- Checking service status
- Reading logs
- Running backend applications
- Thinking about deployment reliability
