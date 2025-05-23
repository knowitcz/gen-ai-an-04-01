# Happy Bank

Happy Bank is an educational project that can be used to explain and demonstrate various concepts and approaches relevant to different roles in software development. Through the workshop, the project will slightly evolve to showcase best practices in API design, database management, testing, and deployment.

The chosen technologies for this project, although it is not intended to be focused on them, are:
- **FastAPI**: A modern, fast (high-performance) web framework for building APIs with Python 3.7+ based on standard Python type hints.
- **SQLite**: A C-language library that implements a small, fast, self-contained SQL database engine.
- **SQLAlchemy**: The Python SQL toolkit and Object Relational Mapper that gives application developers the full power and flexibility of SQL.
- **Pydantic**: Data validation and settings management using Python type annotations.
- **Pytest**: A framework that makes building simple and scalable test cases easy.

There are two ways to setup the project - the native way using `venv` and `pip`, or using `uv`.

## Setup using `uv`

Using `uv` is the recommended way to quickly get started with the project. `uv` is a tool that combines virtual environment management and dependency installation in one command.

### Fetch `uv`

Install `uv` by running one of the following commands in your terminal depending on your operating system:

* On Windows:

    ```powershell
    powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
    ```

* On Unix based systems (MacOS, Linux):

    ```bash
    curl -sSL https://astral.sh/uv/install.sh | bash
    ```

Alternatively, you can install `uv` via `pip`:

```bash
pip install uv
```

### Setup and run

1. Create virtual environment with Python 3.10 (you can specify a different version if you have it installed, but make sure it's 3.10 or higher):

    ```bash
    uv venv -p 3.10
    ```

2. Install the dependencies

    ```bash
    uv sync
    ```

3. Run the server

    ```bash
    uv run uvicorn app.main:app --reload
    ```

## Setup using `venv` and `pip` and run

The precondition for this setup is to have **Python 3.10** or higher installed on your system.

You might need to alter the command slightly depending on your operating system. You may need to use `python3` or pass the full path to the Python executable.

1. Create and activate a virtual environment

    ```bash
    python -m venv venv
    ```

2. Activate the virtual environment. Choose the command that matches your operating system:

  * On Windows:

    ```bash
    venv\Scripts\activate
    ```

  * On Unix based systems (MacOS, Linux):

    ```bash
    source .venv/bin/activate
    ```

3. Install the dependencies

    ```bash
    pip install -e .
    ```

4. Run the server

    ```bash
    uvicorn app.main:app --reload
    ```

Open your browser and navigate to `http://localhost:8000/docs` to access the interactive API documentation provided by FastAPI.

## Database Initialization

Whenever you modify the database models or default data, you should delete the existing SQLite database file (`./app.db`) to apply the changes. The application will automatically create a new database with the updated schema and default data on the next run.
