# GitHub Actions

- [Black - The uncompromising code formatter](https://black.readthedocs.io/en/stable/)
	- `black.yml` specifies a GitHub action that reformats all Python code in your repository, upon pull request, if needed.
	- `black.yml` is configured to be copied into your `.github/workflows` directory directly. The action will run `black . --exclude "\.ipynb$"`, making formatting changes to all non-notebook Python files. If changes are made, a new commit will be added to the PR from "GitHub Actions Bot" with the commit message "files reformatted with black".
- [Pylint - Python static code analyzer](https://pylint.readthedocs.io/en/stable/)
	- `pylint.yml` specifies a GitHub action that analyzes your repository, upon pull request. The check will pass or fail based on the Pylint rating of your code as well as the threshold specified.
	- `pylint.yml` requires reconfiguration. Line 22 should be removed/modified depending on the dependencies needed in your codebase. Line 27 should be edited to change `your/directory` to the directory you want Pylint to analyze. Line 30 can optionally be changed to lower or raise the minimum threshold for the check to pass.
