# linux-env-setup-automation

# Installation & Setup:
Step 1: Create the Shell Script
- Create a file named envsetup with the code from envsetup file.

Step 2: Save the Script
- Save the script as envsetup in a directory of your choice (e.g., /home/kali/).

Step 3: Move the Script to /usr/local/bin
- To make the script accessible system-wide, move it to /usr/local/bin and make it executable:
> sudo mv /home/kali/envsetup /usr/local/bin/

> sudo chmod +x /usr/local/bin/envsetup

Step 4: Test the Script
- Navigate to any directory containing a requirements.txt file and run:
> envsetup

# The script will:
- Check for requirements.txt and python3.12-venv.
- Install python3.12-venv if missing.
- Create and activate the virtual environment.
- Install dependencies from requirements.txt.

# Additional Notes
- Error Handling: The script checks for the existence of requirements.txt and ensures python3.12-venv is installed before proceeding.
- System-Wide Accessibility: By placing the script in /usr/local/bin, it becomes available to all users and can be run from any terminal.
- Customization: If you want to use a different Python version or virtual environment name, modify the script accordingly.

# Usage Example
- Suppose you have a project directory with the following structure:
- my_project/requirements.txt

- Run the following commands:
> cd my_project

> envsetup

The script will set up the virtual environment and install the dependencies listed in requirements.txt.
