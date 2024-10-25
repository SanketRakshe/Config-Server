# Config-Service

The Config Service provides centralized configuration management for all microservices in this project.

## Getting Started

The Config Service is built using Spring Cloud Config Server, which fetches configurations from a local configuration repository.

### Prerequisites

- Java 17
- Maven
- Docker (optional)

### Local Setup Without Docker

1. **Clone the repository**:
    ```bash
    git clone <repository-url>
    cd config-server
    ```

2. **Configure application properties**: Update `src/main/resources/application.properties` as follows:
    ```properties
    spring.application.name=config-server
    server.port=8888
    spring.profiles.active=native
    spring.cloud.config.server.native.search-locations=classpath:/config
    ```

3. **Build the application**:
    ```bash
    mvn clean install
    ```

4. **Run the application**:
    ```bash
    mvn spring-boot:run
    ```

### Local Setup With Docker

1. **Build the Docker image**:
    ```bash
    docker build -t config-server .
    ```

2. **Run the Docker container**:
    ```bash
    docker run -p 8888:8888 config-server
    ```

Your Config Service should now be available at `http://localhost:8888`.
