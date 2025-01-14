# Validate Property Files with GitHub Actions

This repository contains a GitHub Actions workflow to ensure consistency and completeness across environment-specific property files in Maven projects.

## 📜 Overview

This workflow:
- Validates that all properties in the source file are present in the destination files.
- Ensures all non-empty properties in the source file are also non-empty in the destination files.
- Dynamically sets source and destination property files based on the branch (`dev`, `staging`, `main`).

## 🚀 How It Works

1. **Trigger**: The workflow runs on pull requests targeting the `dev`, `staging`, or `main` branches.
2. **Dynamic Configuration**:
    - Source and destination files are determined based on the branch.
3. **Validation Steps**:
    - Compares keys in the source file against destination files.
    - Checks for:
        - Missing keys in destination files.
        - Empty values in destination files for keys that are non-empty in the source file.
4. **Results**:
    - Fails the workflow with a detailed report if any discrepancies are found.

### **How to Use**
1. **Configure Trigger Branches**: Ensure the `branches` section includes all the branches where validation is required (e.g., `dev`, `staging`, `main`).
2. **Set Source and Destination Files**:
   - For each branch, specify:
      - A `source_file`: The file containing the base properties.
      - One or more `destination_files`: The files to be validated against the source.
3. **Add the Workflow File**: Save the file in the `.github/workflows` directory of your repository.
4. **Commit and Push**: Once added, the workflow will automatically trigger on pull requests to the specified branches.

## 📝 Prerequisites

- Ensure your property files are located at the specified paths in your project structure.
- Make sure your GitHub repository has the `.github/workflows` directory.


## ✨ Benefits

- **Improved Consistency**: Ensures all environment-specific property files match the base configuration.
- **Error Prevention**: Avoid runtime issues caused by missing or misconfigured properties.
- **Seamless Integration**: Works out-of-the-box with Maven-based projects in a CI/CD pipeline.

## ✉️ Contributing
Have ideas to enhance this workflow? Feel free to open an issue or submit a pull request! Feedback is always welcome. 😊

## 📄 License
This repository is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.