# ✨ Azure Terraform with Modules ✨

This repository contains Terraform code for quickly setting up the basics of an Azure environment, with a focus on Azure Virtual Desktop (AVD) infrastructure. The modular structure allows for easy customization and scalability.

## Prerequisites

Before you begin, ensure you have:

1. Working knowledge of Terraform and its module system.
2. Terraform configured to work with your Azure environment.
3. An active Azure subscription with necessary permissions to deploy resources.

## 🚀 Getting Started

This project uses a modular structure for better organization and reusability. The root `main.tf` file serves as the entry point and allows for easy customization of variables.

### Structure

- `main.tf` (root): Contains module declarations and variable overrides.
- `Modules/`: Directory containing individual modules for different Azure resources.

### Customization

1. Review the root `main.tf` file.
2. Each module block in `main.tf` corresponds to a subdirectory in the `Modules/` folder.
3. To customize settings, modify the variables in the module blocks.
4. To use default values, leave the variables unspecified.
5. Remove or comment out any module blocks for resources you don't need.

## 🔧 How It Works

1. When you run `terraform apply`, Terraform reads the root `main.tf` file.
2. It then processes each module, applying the configurations defined in the module's own `main.tf` file.
3. Resource names and other values can be referenced across modules using outputs.
   - Example: `module.rg.rg_name` refers to the `rg_name` output from the RG (Resource Group) module.
   - These outputs are defined in each module's `outputs.tf` file.

## 📚 Advanced Usage

- You can use string concatenation, wildcards, and other Terraform functions in the `outputs.tf` files to create dynamic values.
- Explore each module's `variables.tf` file to see all available customization options.

## 🤝 Contributing

Feel free to fork this repository and submit pull requests with improvements or additional modules. Please ensure you follow Terraform best practices and include appropriate documentation.

## 📝 License

This project is licensed under the GNU General Public License v3.0 - see the [LICENSE](LICENSE) file for details.

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
