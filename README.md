# GitHub Actions Automated Workflows

## Purpose of Each Workflow
* **Workflow 1 (Dependent Jobs)**: This workflow ensures that tasks happen in a specific sequence (Build -> Test -> Deploy). It simulates a real-world pipeline where you shouldn't deploy code that hasn't been built or tested.
* **Workflow 2 (Multi-Platform Testing)**: This workflow tests the code across different operating systems (Ubuntu, Windows, and macOS) at the same time to ensure compatibility.

---

## Key Concepts Demonstrated
* **needs**: Used to create dependencies. It forces a job to wait for another job to complete successfully before starting.
* **runs-on**: Defines the operating system (runner) for the job, such as `ubuntu-latest`, `windows-latest`, or `macos-latest`.
* **env**: Used to set environment variables that store data or configuration values for use during steps.

---

## Challenges and Resolutions

* **Challenge**: The workflow did not trigger because it was configured for the `main` branch, but my repository's default branch was actually `master`.
* **Resolution**: I updated the YAML configuration under the `on: push` and `on: pull_request` sections to target the correct branch name.
* **Challenge**: I had issues with the `git pull` command and merging the pull request, which prevented my local code from staying in sync with the repository.
* **Resolution**: I resolved this by committing my local changes first and then using `git pull origin master` to sync the merged changes back to my computer.
