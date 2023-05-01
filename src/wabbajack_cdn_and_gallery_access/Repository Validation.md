# Repository Validation

**This section is important for everyone with merge permissions!**

## General Information

We all know how frequently in the past a broken `.json` file has caused us headaches like a broken gallery in the app and on the website. To fix this, the GitHub Validation for modlist repositories has been updated. It now validates `repositories.json` _and_ the `.json` files linked therein.

The test runs every 4 hours as well as on every pull request and commit made to the `wabbajack-tools/mod-lists` repository.

To check past runs or trigger a new run on the main repository (in case the website and app gallery are broken and you need to find the issue) go to the [Github Actions Tab](https://github.com/wabbajack-tools/mod-lists/actions/workflows/validation.yml)

![run_validation_on_master](assets/run_validation_on_master.webp)

## Merging Procedure

Before merging older pull requests it is recommended to run the validation again **even if they have been previously validated** as the linked `.json` files may have been edited or deleted since. The merging process is as follows:

1. Go to the Details page of the Validation run: </br>
   ![show_validation_run_details](assets/show_validation_run_details.webp)
2. Re-run all jobs: </br>
   ![re-run_all_jobs](assets/re-run_all_jobs.webp)
3. If the run is successful:
    1. In the case of pull request validation, the pull request may now be merged
    2. In the case of a regular validation (not validating a pull request), the gallery is up and in good condition.
4. If the run is unsuccessful, you can find the reason for the test failing in the log under the test section: </br>
   ![failed_run_example](assets/failed_run_example.webp)
   In this example the error was a missing `,` in the `.json` file of the repository that was to be merged.
