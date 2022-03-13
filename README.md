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

# Other Notes

Need to create a recipe file in order to generate a dataset. Snowfakery assumes you already have a file created.

Create a new file in VSCode with extension of `.yml`.

Example Code `test_account.yml`:
`- object: Account
  fields:
    name: 
      fake: company
    BillingStreet:
      fake: street_address
    BillingCity:
      fake: city
    BillingState:
      fake: state
    BillingPostalCode:
      fake: postalcode
    BillingCountry: United States
    ShippingCountry: United States
    Phone:
      fake: phone_number
    Fax:
      fake: phone_number
    Description:
      fake: catch_phrase
    NumberOfEmployees:
      random_number:
        min: 1
        max: 500000`

# Run file locally

`$ snowfakery --output-format JSON --output-file test_account.json test_account.yml`

# Run Script, Creat Records in Salesforce

`$ cci task run generate_and_load_from_yaml -o generator_yaml account.yml --org org-name-goes-here`

