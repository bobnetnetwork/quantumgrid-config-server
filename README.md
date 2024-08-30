# Config Server

The **Config Server** provides centralized configuration management for all microservices in the QuantumGrid platform, allowing dynamic configuration updates.

## Features

- Centralized configuration management
- Dynamic refresh of configuration properties
- Secure configuration storage
- Integration with Git for version-controlled configurations

## Technology Stack

- **Java**: Programming language
- **Spring Boot**: Microservice framework
- **Spring Cloud Config Server**: Configuration server implementation

## Getting Started

### Prerequisites

- **Java 17** or higher
- **Maven** for build automation
- **Git** for storing configuration files

### Setup

1. Clone the repository:
    ```bash
    git clone https://github.com/bobnetnetwork/quantumgrid-config-server.git
    cd quantumgrid-config-server
    ```

2. Configure the Git repository URL for storing configurations in `src/main/resources/application.yml`:
    ```yaml
    spring:
      cloud:
        config:
          server:
            git:
              uri: https://github.com/bobnetnetwork/quantumgrid-config-repo
              default-label: main
    ```

3. Build the application:
    ```bash
    mvn clean install
    ```

4. Run the application:
    ```bash
    mvn spring-boot:run
    ```

### Using Config Server

- Microservices can fetch their configurations by accessing the Config Server endpoint: http://localhost:8888/{application}/{profile}

example: `http://localhost:8888/user-service/dev`

## Contributing

Please read the [CONTRIBUTING.md](https://github.com/bobnetnetwork/quantumgrid/blob/main/CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests.

## License

This project is licensed under the GPL-3.0 license - see the [LICENSE.md](https://github.com/bobnetnetwork/quantumgrid/blob/main/LICENSE.md) file for details.
