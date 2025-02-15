# OpenAPI Spring Boot Generator

This project demonstrates how to generate a fully functional Spring Boot server using an OpenAPI specification (openapi.yaml) and the OpenAPI Generator CLI (openapi-generator-cli.jar).

## 📂 Project Structure

```
.
├── openapi-generator-cli.jar  # OpenAPI Generator CLI JAR
└── openapi.yaml               # OpenAPI Specification file
```

## 🔧 Prerequisites

Before running the generator, ensure you have installed the following dependencies:

## 1️⃣ Install Java 17+

Make sure you have Java installed (Java 17+ recommended). If not, install it via:

```sh
sudo apt update && sudo apt install openjdk-17-jdk  # Ubuntu/Debian
brew install openjdk@17                              # macOS (Homebrew)
```

Check installation:

```sh
java -version
```

## 2️⃣ Install OpenAPI Generator CLI

If openapi-generator-cli is not installed globally, download it manually:

```sh
wget https://repo1.maven.org/maven2/org/openapitools/openapi-generator-cli/7.2.0/openapi-generator-cli-7.2.0.jar -O openapi-generator-cli.jar
```

Then create an alias for easier execution:

```sh
alias openapi-generator-cli="java -jar $(pwd)/openapi-generator-cli.jar"
```

To make the alias permanent, add it to your ~/.zshrc (or ~/.bashrc for Bash users):

```sh
echo 'alias openapi-generator-cli="java -jar $(pwd)/openapi-generator-cli.jar"' >> ~/.zshrc
source ~/.zshrc
```

## 🚀 Generating the Spring Boot Application

Run the following command from the root directory to generate the Spring Boot project:

```sh
openapi-generator-cli generate -i openapi.yaml -g spring -o .
```

This will generate a Spring Boot project in the current directory based on openapi.yaml.

## 🛠 Running the Spring Boot Application

After generating the project, install dependencies and run the server:

```sh
mvn clean install
mvn spring-boot:run
```

## 📝 Notes

Ensure your openapi.yaml is valid before generating the project.

If the generated files are not placed correctly, adjust --package-name in the generator command.

For a different output directory, specify -o <directory> in the generation command.
