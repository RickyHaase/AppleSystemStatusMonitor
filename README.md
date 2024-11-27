# Apple System Status Monitor
 Program to log errors reported by the Apple System Status page

## Motivation
 Apple only gives real-time insight into system status on their [System Status Page](https://www.apple.com/support/systemstatus/) with no insight into historical issues.

 I use iCloud Private Relay for virtually all my web traffic and at times notice issues with speed or my ability to connect to websites that I regularly visit. When I go to check the System Status Page, there is never any reported issue. I want to monitor this page to see if there are ever any reported issues and to see if they align with the times that I experience problems.

## Plan
 I want to learn GoLang and it seems as though it should be a fairly good fit for this project where I just need a simple binary running as a Systemd service.

 The first output method planned is just a simple log to stdout that can be read from Journalctl.

 Once I have that working reliably, I want to run a simple HTTP server on localhost with slugs for each service that I am interested in monitoring. I will then run an instance of [Uptime Kuma](https://github.com/louislam/uptime-kuma) on the same VM which can give me a nice visual interface and web page to visualize changes.

## Setup Instructions


## Roadmap
- [ ] 0.1 - Polls Apple's Status Page every 60 seconds and outputs changes in iCloud Private Relay to stdout (additional requirements: GitHub automated builds and instructions to get binary running as systemd service with logs in journalctl).
- [ ] 0.2 - Config file to choose which of Apple's services to monitor status for and adjust polling rate.
- [ ] 0.3 - HTTP server with slugs for each service (e.g., example.com/privaterelay) that returns the JSON for just that service with HTTP codes for good or error (additional requirements: add instructions for Uptime Kuma integration).
- [ ] 0.4 - Option (config file) to not regularly poll Apple but instead to do it ad hoc when a GET request is received at the web server.
- [ ] 0.5 - Optional directory (or SQLite/S3 store?) to stash full JSON exports whenever a service status changes.
- [ ] 0.6 - SQLite database to store statistics (not sure what stats I'm interested in or how I would structure the data but if I'm still interested in this project by the time I make it to here, I'm sure I'll have some idea).
