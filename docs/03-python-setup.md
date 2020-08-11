# Python Environment Setup

## Navigation

- [Terminal and Package Manager Setup](01-terminal-setup.md)
- [UNIX-based Command Line Basics](02-unix-basics.md)
- **Python Environment Setup**

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

Microsoft has kindly documented the full process at: https://docs.microsoft.com/en-us/windows/python/web-frameworks

Please complete the following sections of that documentation:

✅ Set up your development environment  
✅ Install Windows Subsystem for Linux **(NOTE: we [covered this already](01-terminal-setup-win.md))**  
✅ Set up Visual Studio Code  
✅ Create a new project  
✅ Install Python, pip, and venv  
✅ Create a virtual environment  
✅ Open a WSL - Remote window  
✅ Install the Microsoft Python extension  
✅ Run a simple Python program  

At this stage you do **not** need to complete the following sections of that documentation:

🚫 Hello World tutorial for Flask  
🚫 Hello World tutorial for Django