# ISAC-Research-Notes

This repository contains research notes and supporting files for the ISAC project.

## Create a conda environment with Miniforge

I use Miniforge (a lightweight conda distribution) to create and manage the Python environment for this project. The repository includes an `environment.yml` at the project root that lists required packages.

Steps to create and manage the environment:

1. Install Miniforge (if you don't already have it).
   - Download and run the Miniforge installer appropriate for your OS/architecture.
   - After installation you may need to initialize your shell (zsh):

```bash
# initialize conda for zsh (run once)
conda init zsh
# then restart your terminal or source the shell config
exec $SHELL
```

If the `conda` command is not found immediately you can also source the Miniforge activate script directly (adjust path if you installed to a different location):

```bash
source ~/miniforge3/bin/activate
```

2. Create the environment from the provided `environment.yml` (this will use the name defined in the file, if present):

```bash
# create using the environment.yml in the repository root
conda env create -f environment.yml
```

If you prefer to set the environment name explicitly, use:

```bash
conda env create -f environment.yml -n isac-research
```

3. Activate the environment:

```bash
conda activate isac-research
# or activate the name declared in environment.yml
```

4. Update the environment after changes to `environment.yml`:

```bash
conda env update -f environment.yml --prune
```

5. Remove the environment (if needed):

```bash
conda env remove -n isac-research
```

6. Quick checks:

```bash
# list environments
conda info --envs
# verify python version
python --version
```