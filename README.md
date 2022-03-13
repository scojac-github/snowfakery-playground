# Installing CumulusCI
From Mac, install `pipx`: 
`$ brew install pipx`
`$ pipx ensurepath`

After `pipx` is installed, install CumulusCI, which includes snowfakery
`$ pipx install cumulusci`

# Starting and initializing a New CumulusCI Project
`$ mkdir new_cci_proj`
`$ cd new_cci_proj`
`$ git init`
`$ cci project init`

# Connect to an org

Connect to a custom domain using `--login-url`

`$ cci org connect <org_name> --login-url https://example.my.domain.salesforce.com`

# Verify Connected Orgs

Use `cci org list` command to see connected orgs