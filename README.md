# SponsorKit Starter Template

## About

`sponsorkit-starter` is a GitHub template repository for [SponsorKit](https://github.com/antfu/sponsorkit/) toolkit for automatically generating sponsors images from GitHub Sponsors.

It is heavily inspired by [antfu/static](https://github.com/antfu/static).

## Repo Template

Setup as a starter template, you can easily generate a new GitHub repository. From the repository homepage, click the "Use this template" button.

## What's Included
* `.github/workflows/scheduler.yml` that runs the SponsorKit action on a schedule every day, for each merge on the _main_ branch, or manually.
* `.env.example` as described in [SponsorKit usage](https://github.com/antfu/sponsorkit/#usage).
* `build.sh` script to generate the sponsors images.
* `package.json` relying on the latest version of SponsorKit and containing the `build` script.
* `sponsor.config.ts` that contains the configuration for the generation of the sponsors images.

## Usage

1. Create a new repository from this template.
1. Change its default settings to have “Read an write permissions” for the “Workflow permissions” option in "Actions" section.
1. Modify `.github/workflows/scheduler.yml` to set your GitHub username for the `SPONSORKIT_GITHUB_LOGIN` environment variable.
1. Create a `SPONSORS_TOKEN` secret in your repository settings with a [GitHub personal access token (classic)](https://docs.github.com/en/github/authenticating-to-github/keeping-your-account-and-data-secure/creating-a-personal-access-token) with the `read:org` and `read:user` scopes.
1. (Optional) Modify the `sponsor.config.ts` file to match your needs.
1. Commit and push your changes to the _main_ branch. It will trigger the workflow, generate and commit the sponsors images at the root level of your repository.

### Manual Generation

You can also generate the sponsors images locally by running the `build.sh` script.

For that, you need to copy `.env.example` to `.env` and set the `SPONSORKIT_GITHUB_TOKEN` and `SPONSORKIT_GITHUB_LOGIN` variables.

And then simply run `npm run build`.
