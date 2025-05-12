# linux-env-setup-automation


EnvSetup Script
A shell script to automate the process of setting up a Python virtual environment and installing dependencies from a requirements.txt file. This script simplifies dependency management and ensures consistency across projects.

Features
Automatically checks for and installs python3.12-venv if not already installed.
Creates a virtual environment named venv.
Activates the virtual environment and upgrades pip.
Installs dependencies from requirements.txt.
Prerequisites
A Linux-based system (tested on Kali Linux).
Python 3.12 or higher installed.
sudo privileges to install python3.12-venv if necessary.

Installation
Step 1: Clone the Repository
git clone https://github.com/your-username/envsetup.git 
cd envsetup

Step 2: Move the Script to /usr/local/bin
To make the script accessible system-wide, move it to /usr/local/bin and make it executable:
sudo mv envsetup /usr/local/bin/
sudo chmod +x /usr/local/bin/envsetup

Step 3: Verify Installation
You can verify that the script is installed correctly by running:
envsetup --help
If the script is installed correctly, you should see a message indicating usage instructions.

Usage
Basic Usage
Navigate to your project directory containing a requirements.txt file and run:
envsetup

The script will:
Check for the presence of requirements.txt.
Install python3.12-venv if not already installed.
Create and activate a virtual environment named venv.
Upgrade pip and install dependencies from requirements.txt.

Example Workflow
Suppose you have a project directory with the following structure:
my_project/
├── requirements.txt
└── main.py

Run the following commands:
cd my_project
envsetup
After execution, the virtual environment will be active, and all dependencies listed in requirements.txt will be installed.

Script Details
Source Code
The script (envsetup) performs the following steps:
Check for requirements.txt: Ensures the file exists in the current directory.
Install python3.12-venv: Checks if python3.12-venv is installed and installs it if missing.
Create Virtual Environment: Creates a virtual environment named venv.
Activate Virtual Environment: Activates the virtual environment.
Upgrade pip: Upgrades pip to the latest version.
Install Dependencies: Installs dependencies from requirements.txt.

Script Content
#!/bin/bash
# Check if requirements.txt exists
if [ ! -f "requirements.txt" ]; then
    echo "Error: requirements.txt not found in the current directory."
    exit 1
fi

# Check if python3.12-venv is installed
if ! dpkg -l | grep -q python3.12-venv; then
    echo "Installing python3.12-venv..."
    sudo apt update
    sudo apt install -y python3.12-venv
fi

# Create a virtual environment named 'venv'
echo "Creating virtual environment..."
python3 -m venv venv

# Activate the virtual environment
echo "Activating virtual environment..."
source venv/bin/activate

# Upgrade pip to the latest version
echo "Upgrading pip..."
pip install --upgrade pip

# Install dependencies from requirements.txt
echo "Installing dependencies from requirements.txt..."
pip install -r requirements.txt

echo "Setup complete. Virtual environment is active."
Contributing
Contributions are welcome! If you find any issues or have suggestions for improvement, feel free to open an issue or submit a pull request.
