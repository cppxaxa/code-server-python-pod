# Code-Server with Python and AI Chat

This Kubernetes YAML file defines a pod that runs a code-server instance with Python support and AI Chat integration.

## Features

- **Code-Server:** Provides a web-based IDE for code editing and development.
- **Python:** Includes the Python 3.11 runtime environment for Python development.
- **AI Chat:** Integrates the AI Chat tool for conversational AI interactions.

## Usage

1. **Deploy the YAML file:** Use `kubectl apply -f code-server-ext.yaml` to deploy the pod.
2. **Access the code-server:** Use `kubectl port-forward pod/code-server 8080:8080` to forward the pod's port 8080 to your local machine. Then, access the code-server in your browser at `http://localhost:8080`.
E.g. kubectl port-forward pod/code-server 8080:8080
3. **Use AI Chat:** The AI Chat tool is available within the code-server environment.

## Configuration

- **Image:** The pod uses the `python:3.11-slim` image, which includes Python 3.11 and essential tools.
- **Volume:** A persistent volume is mounted at `/home/coder/project` for storing project files.
- **Extensions:** The `ms-python.python` extension is installed for Python development.
- **Authentication:** Authentication is disabled for easy access.

## Notes

- The AI Chat tool is installed from the [aichat](https://github.com/sigoden/aichat) repository.
- The code-server installation script is downloaded from [code-server.dev](https://code-server.dev).
- Adjust the configuration as needed for your specific environment.

## License

This project is licensed under the Apache 2.0 License.