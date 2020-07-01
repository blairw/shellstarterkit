# Python Environment Setup

## Navigation

- [Terminal and Package Manager Setup](01-terminal-setup.md)
- [UNIX-based Command Line Basics](02-unix-basics.md)
- **Python Environment Setup**
- [Python web server](04-python-web-server.md)

## macOS

1. Install Python 3 via Homebrew:

    ```bash
    brew install python
    ```

2. Modify the PATH:

    ```bash
    echo '\n\nexport PATH="/usr/local/opt/python/libexec/bin:'$(python -m site --user-base)'/bin:$PATH"' >> ~/.zshrc
    ```

3. Quit Terminal (Command+Q) and re-open it. `python` should now be the latest Python 3.

## Windows (via WSL)

TODO: Windows instructions.

https://docs.microsoft.com/en-us/windows/python/web-frameworks