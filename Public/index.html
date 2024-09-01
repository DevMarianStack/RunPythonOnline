import json
import subprocess
import sys
import io

# Allowed packages for installation
ALLOWED_PACKAGES = {
    "discord.py", "psutil", "colorama", "requests", "numpy",
    "pandas", "matplotlib", "scipy", "flask", "beautifulsoup4",
    "pytest", "sqlalchemy", "jupyter", "sympy", "tensorflow",
    "keras", "scikit-learn", "lxml", "pyyaml"
}

def install_package(package_name):
    if package_name in ALLOWED_PACKAGES:
        try:
            subprocess.check_call([sys.executable, "-m", "pip", "install", package_name])
            return f"Package '{package_name}' installed successfully."
        except subprocess.CalledProcessError as e:
            return f"Failed to install package '{package_name}': {e}"
    else:
        return f"Package '{package_name}' is not allowed."

def safe_exec(code):
    exec_globals = {"__builtins__": {}}
    exec_locals = {}
    
    try:
        exec(code, exec_globals, exec_locals)
        return exec_locals.get("output", "No output")
    except Exception as e:
        return f"Error: {str(e)}"

def handler(request):
    data = request.json
    code = data.get("code", "")
    packages = data.get("packages", "").split()
    
    output = []

    for package in packages:
        output.append(install_package(package))

    old_stdout = sys.stdout
    sys.stdout = io.StringIO()
    
    output.append(safe_exec(code))
    
    sys.stdout = old_stdout
    return json.dumps({"output": sys.stdout.getvalue(), "messages": output})
