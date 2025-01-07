# Development Docker Compose Configurations

This repository contains various `docker-compose` configurations designed to simplify local development. Each configuration provides a ready-to-use setup for commonly used services, helping you quickly spin up development environments.

## Available Configurations

### PostgreSQL (Version 16)
A `docker-compose` setup for PostgreSQL 16, configured for development purposes. This setup allows you to run PostgreSQL locally without requiring a password or predefined databases, making it ideal for quick prototyping.

> [!NOTE]
> This setup is intended for development only. Do not use it in production as the authentication configuration (trust) is not secure. You can modify the exposed port or other settings by editing the docker-compose.yml file.

#### Features:
- **PostgreSQL Version**: 16
- **Authentication**: Configured with `POSTGRES_HOST_AUTH_METHOD=trust` to bypass password requirements.
- **Default User**: Uses the default `postgres` user without a password.
- **Ports**: Exposes PostgreSQL on port `5432` (or configurable).

#### Usage:
1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd <repository-folder>
   ```


2. Navigate to the PostgreSQL directory:
    ```bash
    cd postgresql
    ```

3. Start the container:
    ```bash
    docker compose up -d
    ```

4. Stop the container when done:
    ```bash
    docker compose down
    ```

#### Troubleshooting
If you encounter an error stating that port 5432 is already in use, it is likely that another PostgreSQL service is running on your system. To stop the default PostgreSQL service:

##### On Linux:
1. Check the status of the PostgreSQL service:
    ```bash
    sudo systemctl status postgresql
    ```

2.  Stop the service:
    ```bash
    sudo systemctl stop postgresq
    ```

##### On macOS:
If PostgreSQL is installed via brew:
1. Check the status of the PostgreSQL service:
    ```bash
    brew services list
    ```

2.  Stop the service:
    ```bash
    brew services stop postgresql
    ```


## Contributing
If you have suggestions or configurations to add, feel free to open a pull request or create an issue. Contributions are welcome!

## License
This project is licensed under the MIT License.