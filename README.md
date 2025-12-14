# Azure DevOps Pipeline Examples

Practical Azure DevOps YAML pipeline examples for build, test, and deployment workflows. These are production-tested patterns demonstrating multi-stage builds, artifact management, and deployment validation.

## Contents

- **azure-pipelines.yml** - Complete multi-stage pipeline (build → test → deploy)
- **windows-image-deployment.yml** - Windows image build, validation, and device deployment pipeline
- **device-provisioning.yml** - Automated device provisioning with testing

## Quick Start

These YAML files are ready to use in Azure DevOps. Copy the pipeline YAML into your Azure DevOps project:

1. Create a new pipeline in Azure DevOps
2. Select "Existing Azure Pipelines YAML file"
3. Choose the YAML file from this repo
4. Customize variables and paths for your environment

## Key Concepts

Each pipeline demonstrates:
- **Multi-stage builds** - Separating build, test, and deployment stages
- **Artifact management** - Creating, storing, and retrieving build artifacts
- **Template reuse** - Using shared job/step templates to reduce duplication
- **Environment gating** - Approval gates between environments
- **Error handling** - Proper failure detection and reporting
- **PowerShell integration** - Using properly named PowerShell scripts with approved verbs

## Customization

All pipelines use variables at the top for easy customization:
- `buildConfiguration` - Debug/Release
- `imageVersion` - Version numbering
- `deploymentTarget` - Environment targets
- `artifactPath` - Artifact storage locations

## PowerShell Scripts

All referenced PowerShell scripts use approved verb naming conventions for operational clarity and maintainability. See the [PowerShell Design Philosophy](https://github.com/chad-holle/infrastructure-documentation/blob/main/POWERSHELL_DESIGN_PHILOSOPHY.md) for details.

Example script references:
- `Write-LogMessage.ps1` - Output/log messages
- `Initialize-Devices.ps1` - Setup and provision devices
- `Test-Drivers.ps1` - Validate driver packages
- `Invoke-DeploymentValidation.ps1` - Execute deployment validation

## Notes

These are production-tested patterns. Adjust for your specific needs but the underlying structure has proven reliable.

## See Also

- [Infrastructure Documentation](https://github.com/chad-holle/infrastructure-documentation) - Design philosophy and guides
- [PowerShell Deployment Toolkit](https://github.com/chad-holle/powershell-deployment-toolkit) - The scripts these pipelines call
