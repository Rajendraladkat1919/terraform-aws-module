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



1. Install pre-commit: If you don't have pre-commit installed, you can install it by running:

```
pip install pre-commit or brew install pre-commit
```

2. Create .pre-commit-config.yaml file: This file defines the hooks.

'''
# .pre-commit-config.yaml
- repo: https://github.com/terraform-linters/tflint
  rev: v0.29.0  # Use the latest version or specify a version
  hooks:
    - id: tflint
      name: "TFLint - Terraform Linter"
      description: "This hook checks your Terraform files for mistakes using TFLint."
      files: \.tf$

- repo: https://github.com/aquasecurity/tfsec
  rev: v1.17.0  # Use the latest version or specify a version
  hooks:
    - id: tfsec
      name: "tfsec - Terraform Security Scanner"
      description: "This hook runs tfsec, a security scanner for Terraform."
      files: \.tf$

- repo: https://github.com/terraform-docs/terraform-docs
  rev: v0.16.0  # Use the latest version or specify a version
  hooks:
    - id: terraform-docs
      name: "Terraform Docs"
      description: "This hook generates Terraform documentation automatically."
      files: \.tf$

- repo: https://github.com/pre-commit/mirrors-terraform
  rev: v0.10.0  # Use the latest version or specify a version
  hooks:
    - id: terraform-fmt
      name: "Terraform fmt"
      description: "This hook ensures that Terraform files are formatted correctly."
      files: \.tf$

- repo: https://github.com/pre-commit/mirrors-check-json
  rev: v2.0.0  # Use the latest version or specify a version
  hooks:
    - id: check-json
      name: "Check JSON"
      description: "This hook checks that JSON files are valid."
      files: \.json$

- repo: https://github.com/pre-commit/mirrors-check-yaml
  rev: v0.2.0  # Use the latest version or specify a version
  hooks:
    - id: check-yaml
      name: "Check YAML"
      description: "This hook checks that YAML files are valid."
      files: \.yaml$

- repo: https://github.com/pre-commit/mirrors-check-shebang
  rev: v0.1.0  # Use the latest version or specify a version
  hooks:
    - id: check-shebang
      name: "Check Shebang"
      description: "This hook ensures the files have the correct shebang line."
      files: \.sh$
'''

3. # Make sure below tools install with homebrew.
'''
tflint --version
tfsec --version
terraform-docs --version
terraform fmt --version
check-json --version
check-yaml --version
check-shebang --version
'''
4. Run pre-commit install to enable the hooks for Git.

5. Run pre-commit run --all-files to manually apply the hooks to all files.