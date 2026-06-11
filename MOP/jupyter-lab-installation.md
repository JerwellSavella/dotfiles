# Installation Guide

- First part is determine which environment manager to use for machine learning, There's 3 package and environment manager available: PIP, MAMBA and CONDA. 

Direct Breakdown: Why One Wins Over the Other

1. Mamba (The Modern Gold Standard)Mamba is a drop-in, open-source replacement for Conda. It uses the exact same package channels (like conda-forge) but swaps Conda's slow Python-based management engine for a lightning-fast C++ solver.
- Why it's better: It installs JupyterLab and complex data science packages (like PyTorch or TensorFlow) in seconds, whereas Conda can sit "freezing" or "solving environment" for 20 minutes.
- Best for: Anyone doing serious data science, machine learning, or working with complex environments on Ubuntu.

2. Conda (The Trusted Veteran)Conda is an environment and package manager combined. Unlike pip, it can install non-Python software dependencies that tools like NumPy or SciPy need to run smoothly.
- Why it's good: It is bulletproof at keeping environments isolated and stable.
- The downside: As your environment grows, Conda becomes notoriously slow at calculating package updates.
- Best for: Users who want maximum stability and don't mind waiting a bit longer for installations.

3. Pip (The Lightweight Specialist)Pip is Python’s official package manager. It is what you just used in your previous step.
- Why it's good: It is fast, lightweight, and comes built into Python. It has the largest repository of Python packages (PyPI).
- The downside: It cannot handle system-level dependencies. If a Python data science tool requires a specific C++ tool compiled on your Ubuntu system, pip will fail, forcing you to manually install it via sudo apt.
- Best for: Pure Python development, minimal environments, or when you are running on low-resource hardware like a Raspberry Pi.






# PIP 
## Virtual Environment (Recommended)

1. Install Environment Manager: `sudo apt install python3-venv -y`
2. Create a folder and a new environment: `mkdir ~/jupyter_projects && cd ~/jupyter_projects`
3. `python3 -m venv my_env`
4. Activate it: `source my_env/bin/activate`
5. Install JupyterLab inside this space: `pip install jupyterlab`


## System Wide install using pipx (Use only if you have a dedicated python server)
1. install pipx: `sudo apt install pipx -y` and `pipx ensurepath` then restart your terminal so it recognizes the new setup 
2. Install JupyterLab globally: `pipx install jupyterlab`
3. Launch it immediately by typing: `jupyter lab`


# USING MAMBA (Personal Choice)
1. Download and Install Miniforge 
1. Open your terminal and download the latest Miniforge installer for Linux using wget:
`wget https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-Linux-x86_64.sh`
2. Run the installer script: `bash Miniforge3-Linux-x86_64.sh`
3. Follow the terminal prompts:
- Press Enter to review the license agreement, then type yes to accept it.
- Press Enter to accept the default installation location (usually ~/miniforge3).
- When asked: "Do you wish to update your shell profile to automatically initialize conda?", type yes.
4. Apply Changes: Close your terminal window and open a fresh one, or run this command to refresh your current session: `source ~/.bashrc` `source ~/.zshrc`

2. Configure Terminal Behavior (Optional but Recommended)
By default, Mamba will auto-activate its (base) environment every time you open a terminal. If you want your normal Ubuntu terminal back and prefer to activate Mamba manually, disable auto-activation with this command:
`conda config --set auto_activate_base false`

3. Create a Mamba Environment $ Install JupyterLab
Never install packages directly into your (base) environment, as it can cause software conflicts later. Always create a separate project sandbox.
1. Create a new environment named data_env and install JupyterLab along with standard data tools (Pandas, NumPy, Matplotlib) simultaneously: `mamba create -n data_env jupyterlab pandas numpy matplotlib -y`


4. Activate and Run JupyterLab
Whenever you want to work on your notebooks, run these two quick commands: `mamba activate data_env`
`jupyter lab`







