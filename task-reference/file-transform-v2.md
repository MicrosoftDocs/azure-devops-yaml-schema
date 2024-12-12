# FileTransform@2 Task in Azure DevOps

## Overview
The `FileTransform@2` task in Azure DevOps pipelines is used to transform configuration files such as JSON, XML, YAML, and more. It is particularly useful for replacing tokens or applying transformations to configuration files during deployment.

---

## Features

1. **Supports Multiple Formats**:
   - JSON, XML, and YAML file types are natively supported.

2. **Token Replacement**:
   - Replace placeholders in configuration files with values from pipeline variables, variable groups, or Key Vault secrets.

3. **Custom Token Prefix/Suffix**:
   - Customize the format of tokens in your configuration files (e.g., `__TokenName__`, `{{TokenName}}`).

4. **File Type Detection**:
   - Automatically detects the file type or allows manual specification.

5. **Flexible Targeting**:
   - Use glob patterns to target multiple files for transformation.

6. **Override Parameters**:
   - Provide custom values directly in the task for specific transformations.

---

## Common Use Cases

1. **Environment-Specific Configurations**:
   - Replace values like API URLs, connection strings, or other environment-specific settings.

2. **Integration with Key Vault**:
   - Securely replace sensitive tokens like secrets and API keys.

3. **Multiple File Transformation**:
   - Apply changes to multiple files at once using glob patterns.

---

## Task Schema

### Basic Syntax
```yaml
- task: FileTransform@2
  inputs:
    folderPath: '<path-to-folder>'
    targetFiles: '<glob-pattern>'
    fileType: '<file-type>'
    tokenPrefix: '<custom-prefix>'
    tokenSuffix: '<custom-suffix>'
    overrideParameters: |
      Key1=Value1
      Key2=Value2
```

---

## Parameters

### Required Inputs
- **`folderPath`**: Path to the directory containing configuration files.
- **`targetFiles`**: Glob pattern specifying files to transform (e.g., `**/*.json`).

### Optional Inputs
- **`fileType`**:
  - Specifies the file type (`json`, `xml`, `yaml`).
  - Default: Auto-detect based on file extension.
- **`tokenPrefix`**: Custom prefix for tokens (e.g., `__`).
- **`tokenSuffix`**: Custom suffix for tokens (e.g., `__`).
- **`overrideParameters`**:
  - Inline key-value pairs to override tokens (e.g., `Key=Value`).

---

## Examples

### **1. JSON Transformation**
#### appsettings.json
```json
{
  "ApiSettings": {
    "BaseUrl": "__ApiBaseUrl__"
  }
}
```

#### Pipeline YAML
```yaml
trigger:
- main

stages:
- stage: Deploy
  variables:
    ApiBaseUrl: "https://api.example.com"
  jobs:
  - job: Transform
    steps:
    - task: FileTransform@2
      inputs:
        folderPath: '$(Pipeline.Workspace)/config'
        targetFiles: '**/appsettings.json'
        fileType: 'json'
        tokenPrefix: '__'
        tokenSuffix: '__'
```
#### Transformed appsettings.json
```json
{
  "ApiSettings": {
    "BaseUrl": "https://api.example.com"
  }
}
```

### **2. XML Transformation**
#### Web.config
```xml
<configuration>
  <appSettings>
    <add key="ApiBaseUrl" value="__ApiBaseUrl__" />
  </appSettings>
</configuration>
```

#### Pipeline YAML
```yaml
variables:
  ApiBaseUrl: "https://api.example.com"

steps:
- task: FileTransform@2
  inputs:
    folderPath: '$(Pipeline.Workspace)/config'
    targetFiles: '**/Web.config'
    fileType: 'xml'
    tokenPrefix: '__'
    tokenSuffix: '__'
```
#### Transformed Web.config
```xml
<configuration>
  <appSettings>
    <add key="ApiBaseUrl" value="https://api.example.com" />
  </appSettings>
</configuration>
```

---

## Advanced Features

### 1. **Token Customization**
Use `tokenPrefix` and `tokenSuffix` for custom token formats.

#### Example:
```yaml
inputs:
  tokenPrefix: '{{'
  tokenSuffix: '}}'
```
Matches tokens like `{{TokenName}}`.

### 2. **Override Parameters**
Inline overrides take precedence over pipeline variables.

#### Example:
```yaml
inputs:
  overrideParameters: |
    ApiBaseUrl=https://override.api.com
    ExternalServiceBaseUrl=https://override.external.api
```

### 3. **Integration with Key Vault**
Combine with the `AzureKeyVault@2` task to fetch secrets and inject them as pipeline variables for transformation.

#### Example:
```yaml
- task: AzureKeyVault@2
  inputs:
    azureSubscription: '$(azureServiceConnection)'
    KeyVaultName: 'my-key-vault'

- task: FileTransform@2
  inputs:
    folderPath: '$(Pipeline.Workspace)/config'
    targetFiles: '**/appsettings.json'
    fileType: 'json'
```

---

## Debugging Tips

1. **Validate Transformed Files**:
   Add a task to print the transformed files for verification:
   ```yaml
   - script: |
       cat $(Pipeline.Workspace)/config/appsettings.json
   ```

2. **Check Token Matching**:
   Ensure your token prefix and suffix match the placeholders in your files.

3. **Test with Override Parameters**:
   Use `overrideParameters` to test specific transformations without modifying the pipeline variables.

---

## Best Practices

1. **Use Standardized Tokens**:
   Define a consistent token format for all configuration files.

2. **Secure Secrets**:
   Fetch sensitive values like connection strings from Azure Key Vault.

3. **Minimize Variable Redundancy**:
   Use variable groups or Key Vault to centralize configuration management.

---

## References
- [Azure DevOps FileTransform Task Documentation](https://learn.microsoft.com/en-us/azure/devops/pipelines/tasks/utility/file-transform?view=azure-devops)
- [Azure Key Vault Task Documentation](https://learn.microsoft.com/en-us/azure/devops/pipelines/tasks/deploy/azure-key-vault?view=azure-devops)

