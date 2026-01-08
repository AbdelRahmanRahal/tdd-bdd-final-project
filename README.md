# TDD/BDD Final Project

This project demonstrates the application of Test Driven Development (TDD) and Behavior Driven Development (BDD) methodologies to build a robust web service.

## Overview

The project follows Agile development practices to ensure high code quality:

- **TDD**: Unit tests are implemented in the `tests/` directory to drive the development of the application logic.
- **BDD**: Acceptance tests are defined in Gherkin syntax within the `features/` directory to verify the application's behavior from a user's perspective.

## Project Structure

- `service/`: Contains the main application source code and business logic.
- `tests/`: Contains unit tests executed via `nosetests` (TDD).
- `features/`: Contains Cucumber feature files and step definitions executed via `behave` (BDD).
- `bin/`: Contains utility scripts for environment setup.

## Environment Setup

A setup script is provided by IBM to provision the development environment, including Python 3.9, virtual environment configuration, and database setup.

To initialize the environment, run:

```bash
bash bin/setup.sh
```

This script performs the following:

1.  Installs Python 3.9 and creates a virtual environment.
2.  Installs Selenium and Chrome drivers for BDD UI testing.
3.  Installs Python dependencies from `requirements.txt`.
4.  Starts a PostgreSQL database container using Docker. (I think anyway)

## Running Tests

### Unit Tests (TDD)

To run the unit tests, execute:

```bash
nosetests
```

### Acceptance Tests (BDD)

To run the behavioral tests, start the service first by running:

```bash
honcho start
```

Then in a separate terminal, run:

```bash
behave
```

_Note: For BDD tests, the application server must be running. The project includes a VS Code task ("BDD tests") that automatically starts the server, runs the tests, and shuts down the server._

## License

This project is licensed under the Apache License, Version 2.0.
