## 🚀 Quick Start (Windows)

This demo is intentionally simple.

### 1. Install Python

Download and install Python (version 3.10 or newer):

https://www.python.org/downloads/

During installation on Windows, make sure you check:

☑ Add Python to PATH

---

### 2. Open PowerShell and Verify Python

Open **PowerShell** (press Windows key → type "PowerShell").

Verify Python is installed:

    python --version

You should see a version number.

---

### 3. Navigate to the Project Folder

Use the `cd` command to move to the folder where the project is located.

Example:

    cd "C:\Users\YourName\Downloads\controlled-agent-loop"

(You can copy the folder path from File Explorer and paste it.)

Make sure you are inside the project folder before running the next commands.

---

### 4. Install Required Packages

Once inside the project folder, run:

    pip install -r requirements.txt

This installs the required Python libraries.

Note: `requirements.txt` is a common filename used to list dependencies.  
If your project uses a different filename, adjust the command accordingly.

---

### 5. Run the Script

Run the main program:

    python main.py

Outputs will be written to the `output/` folder.

Note: `main.py` is used here as an example name for the primary script.  
Use the actual script name provided in the project (for example: `run_role_check.py`).

---

### Notes

- The setup process is usually the hardest part for first-time users.
- After Python is installed, running the agent only requires a single command.
- Running from PowerShell or Terminal is recommended to avoid environment or path issues.

---

### Optional: Using an Editor (Sublime, VSCode, etc.)

While the demo can be run entirely from PowerShell or Terminal,  
many users prefer editing the code in a programming editor such as  
Sublime Text or Visual Studio Code.

Typical workflow:

1. Open the project folder in your editor.
2. Edit configuration or prompts as desired.
3. Run the script from a terminal:

       python main.py

Some editors also allow running Python directly from inside the editor  
using build systems or extensions, but this is optional.  
The command-line approach above works universally across systems.
