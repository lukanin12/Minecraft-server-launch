# Minecraft GitHub Actions Server

This repository contains the configuration for automatically deploying and managing a Minecraft server using GitHub Actions, playit.gg, and Cloudflare Tunnel.

## Features

- Automated server deployment with GitHub Actions
- Easy server management and monitoring through GitHub Actions
- Remote access using playit.gg tunneling service
- Secure access via Cloudflare Tunnel

## Setup

### Fork the Repository

1. **Fork this repository** to your GitHub account.

### Create Repository Secrets

1. **`FINE_GRAINED_PAT`**:
   - Generate a Fine-Grained Personal Access Token (PAT) with full read and write access to the repository.
   - Navigate to GitHub Settings > Developer Settings > Personal Access Tokens > Fine-grained tokens.
   - Create a new token with appropriate permissions.
   - Copy the generated token.
   - In your forked repository, go to **Settings > Secrets and variables > Actions**.
   - Create a new repository secret named `FINE_GRAINED_PAT` and paste the token as its value.

2. **`PLAYIT_SECRET`**:
   - Install and run the playit.gg tunnel service on your local machine.
   - Extract the data from the generated `playit.toml` file.
   - In your forked repository, go to **Settings > Secrets and variables > Actions**.
   - Create a new repository secret named `PLAYIT_SECRET` and paste the extracted data as its value.

3. **Cloudflare Tunnel Setup**:
   - **Generate a Cloudflare Tunnel certificate**:
     - Follow the [Cloudflare Tunnel documentation](https://developers.cloudflare.com/cloudflare-one/connections/connect-apps/) to generate a certificate.
   - **Retrieve your Cloudflare Tunnel UUID**:
     - Obtain the UUID from the Cloudflare dashboard or using the Cloudflare Tunnel CLI.
   - **Extract the credentials content**:
     - Generate or retrieve the Cloudflare Tunnel credentials file content.

   - In your forked repository, create the following repository secrets:
     - **`CF_CERT`**: Paste the Cloudflare Tunnel certificate data.
     - **`CF_TUNNEL_UUID`**: Paste the UUID of your Cloudflare Tunnel.
     - **`CF_TUNNEL_UUID_CONTENT`**: Paste the content for the Cloudflare Tunnel credentials file.

### Customize Server Settings

1. Modify the `server.properties` file according to your preferences.

### Push Changes

1. **Push your changes** to the repository to trigger the GitHub Actions workflow.

## Usage

- The server will automatically start when you push changes to the repository or based on the scheduled workflow.
- Manage the server using GitHub Actions workflows in the "Actions" tab.
- Access your server using the [playit.gg](https://playit.gg) tunnel address provided in the workflow logs.
- The server will commit and push changes every 30 seconds and automatically clean up old workflow runs to maintain repository health.

## Important Notes

- Public repositories get 16 GB of memory for GitHub Actions, while private repositories only get 8 GB.
- The setup supports both public and private repositories. For private repositories, additional configuration might be required to handle server data.
- This project does **NOT** necessarily need cloudflare or a domain to host a server on github, view [playit-only](https://github.com/Briiqn/Actions-Server/tree/playit-only) for more details, forks may have to make small modifications to make it work.
## Demos

- **BungeeCord**: githubservers.org  or 147.185.221.21:57738
- **Normal**: *Coming soon*

## Contributing

Contributions are **NOT** allowed.

## License

This project is not licensed. Use it as you wish.
