# terraform-aws-module
structuring and Deploying terraform module using best practices and security best practices.

# Things consider while building terraform module.

1. Git repositories
2. Commit Strategy.
3. module release process.
4. pre-commit hook
5. module testing

# pre-commit integration during development.

1. checked-added-large files
2. check-json
3. check-shebang
4. check-toml
5. check-yaml
6. end-of-file-fixer
7. trailing-whitespace
8. terraform fmt
9. terraform-docs
10. tflint
11. tfsec
12. gitleaks


# Setup

pip install pre-commit

Below tools installation.

Terraform
terrafor-docs
terraform-lint
tfsec
gitleaks

add pre-commit-config.yaml

# Steps:

Install pre-commit: If you don't have pre-commit installed, you can install it by running:

```
pip install pre-commit
```

Create .pre-commit-config.yaml file: This file defines the hooks.