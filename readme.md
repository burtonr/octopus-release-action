# OctopusDeploy GitHub Action for Creating a Release
This is a GitHub Action that will create a new "Release" in OctopusDeploy

**This is not an official OctopusDeploy project**

The "work" is done in the [octopus-action-client](https://github.com/burtonr/octopus-action-client) Docker container. 

This repository is to create the `action.yml` and publish to the GitHub Actions Marketplace

## Inputs

### `octopus_url`

**Required** The full URL of your OctopusDeploy instance

> Example: `https://your.octopus.com/`

### `api_key`

**Required** The OctopusDeploy API key used to authenticate with your OctopusDeploy instance

More information here: [How to Create an API Key](https://octopus.com/docs/octopus-rest-api/how-to-create-an-api-key)

### `project_name`

**Required** The Project name to create the release for

### `release_version`

***Required** The version to use for the release

> Example: `"1.0.0"`

### `space_name`

_Optional_ The OctopusDeploy Space the project is located in

More information here: [Spaces](https://octopus.com/docs/administration/spaces)

## Example Usage

```yaml
uses: burtonr/octopus-release-action@master
with:
  octopus_url: 'https://your.octopus.com'
  api_key: ${{ secrets.OCTOPUS_API_KEY }}
  project_name: 'Awesome Project'
  release_version: ${{ github.ref }}
```