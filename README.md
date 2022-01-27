# Create Authorized Keys from Github Teams Action
Automatically create an authorized_files for ssh configuration based on Github Teams' Users Public Keys. 

## Prerequisites
#### Create a Sentry Internal Integration
 - Have a Github Organization and a Team
 - Your github token should be allowed to read the org, o you should add a custom token.

## Usage
Adding the following to your workflow will create an authorized_keys file based on team `foo` of organization `Bar`.
  
```yaml
- uses: actions/checkout@v2
- name: Create Sentry release
  uses: actions/generate-authorized-keys-from-github-teams@v1
    with:
      team: foo
      org: Bar
```

### Inputs
#### Parameters
|name|description|default|
|---|---|---|
|`org`|Github Organization.|-|
|`team`|Organization Team.|-|
|`github-token`|Github token to use.|`github.token`|
|`path`|Where to store the authorized_keys file.|`github.workspace`|
