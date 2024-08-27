# XMRig Docker Setup

This repository provides a Docker setup for running XMRig, a popular cryptocurrency mining software. This guide will help you configure and run the XMRig container using Docker.

## Prerequisites

- Docker installed on your machine
- Docker Compose installed on your machine

## Configuration

Before running the Docker container, you need to configure the environment variables in the `.env.example` file.

1. **Clone the repository** (if applicable):
   ```bash
   git clone <repository-url>
   cd <repository-directory>
   ```

2. **Create a `.env` file**:
   Copy the `.env.example` file to a new file named `.env`:
   ```bash
   cp .env.example .env
   ```

3. **Edit the `.env` file**:
   Open the `.env` file in a text editor and fill in the required values:
   ```plaintext
   XMRIG_VERSION=6.22.0
   WALLET_ADDRESS=<your_wallet_address>  # Replace with your actual wallet address
   COIN_PREFIX=ADA                        # Change if you are mining a different coin
   WORKER_NAME=unmineable_worker_yipllstp # Customize your worker name
   REFERRAL_CODE=#p31b-3n9d               # Optional: Add your referral code if needed
   ```

## Running the Docker Container

1. **Build and start the container**:
   In the terminal, run the following command:
   ```bash
   docker-compose up -d --build
   ```

   This command will build the Docker image and start the XMRig container in detached mode.

2. **Check the logs**:
   To view the logs and monitor the mining process, use:
   ```bash
   docker-compose logs -f
   ```

3. **Stop the container**:
   To stop the mining process, run:
   ```bash
   docker-compose down
   ```

## Notes

- Ensure that your wallet address is correct to receive the mined coins.
- You can customize the `COIN_PREFIX` and `WORKER_NAME` as needed.
- The `REFERRAL_CODE` is optional and can be left blank if not used.

## Troubleshooting

- If you encounter issues, check the logs for error messages.
- Ensure that your Docker installation is working correctly.
- Verify that your wallet address and other configurations are set properly.

## License

This project is licensed under the MIT License. See the LICENSE file for more details.

---

Feel free to modify this README as needed to fit your specific use case or additional instructions!