# Best Practices
## GitHub Actions for Pipelines 

The following describe the minimum GitHub actions that should be deployed with any production pipeline. The actions are automatically provided via the [cookiecutter](https://github.com/CCBR/CCBR_SnakemakePipelineCookiecutter) template.

1. Documentation (assumes `mkdocs build`; required)

    - This rule will automatically update any documentation built with mkdocs for all PR's.

2. Dry-run with test sample data for any PR to dev branch (required)

    - This rule will automatically perform a dry-run with the data provided in the .test folder of the pipeline. Review the [GitHub Best Practices - Test Data](https://ccbr.github.io/HowTos/GitHub/sop_testdata/) page for more information.

3. Full-run with full sample data for any PR to main branch (required)
    - This rule will automatically perform a full-run with the data provided in the .test folder of the pipeline. Review the [GitHub Best Practices - Test Data](https://ccbr.github.io/HowTos/GitHub/sop_testdata/) page for more information.

3. Lintr (required)
    - This rule will automatically perform a lintr with the data provided in the .test folder of the pipeline. Review the [GitHub Best Practices - Test Data](https://ccbr.github.io/HowTos/GitHub/sop_testdata/) page for more information.

4. Auto pull/push from source (if applicable)
    - If the pipeline is forked from another location and updating this forked pipeline is required, an action will automatically perform a pull from the source location at least once a week.