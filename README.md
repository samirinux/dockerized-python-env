# Containerized Development Environment

## Developing inside a Container

For more details refer to [Developing inside a Cpontainer](https://code.visualstudio.com/docs/devcontainers/containers).


## Project Structure

```
my-containerized-dev-env
├── .devcontainer
│   ├── Dockerfile
│   └── devcontainer.json
└── README.md
```

## Getting Started

To get started with this project, follow these steps:

1. **Clone the repository**:
   ```
   git clone <repository-url>
   cd my-containerized-dev-env
   ```

2. **Open in your development environment**:
   Open the project in your preferred development environment that supports Docker.

3. **Build the container**:
   The container will be built automatically based on the configuration in the `.devcontainer` directory.

4. **Install dependencies**:
   The required Python packages will be installed automatically from `requirements.txt` when the container is built.

## Usage

To run the application, use the following command inside the container:

```
python src/main.py
```

## Contributing

Contributions are welcome! Please feel free to submit a pull request or open an issue for any suggestions or improvements.