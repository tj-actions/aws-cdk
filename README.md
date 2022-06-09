[![CI](https://github.com/tj-actions/aws-cdk/workflows/CI/badge.svg)](https://github.com/tj-actions/aws-cdk/actions?query=workflow%3ACI)
[![Update release version.](https://github.com/tj-actions/aws-cdk/workflows/Update%20release%20version./badge.svg)](https://github.com/tj-actions/aws-cdk/actions?query=workflow%3A%22Update+release+version.%22)
[![Public workflows that use this action.](https://img.shields.io/endpoint?url=https%3A%2F%2Fused-by.vercel.app%2Fapi%2Fgithub-actions%2Fused-by%3Faction%3Dtj-actions%2Faws-cdk%26badge%3Dtrue)](https://github.com/search?o=desc\&q=tj-actions+aws-cdk+path%3A.github%2Fworkflows+language%3AYAML\&s=\&type=Code)

## aws-cdk

Run [AWS CDK](https://docs.aws.amazon.com/cdk/v2/guide/getting_started.html) commands

```yaml
...
    steps:
      - uses: actions/checkout@v2
      ...
     
      - name: Install dependencies
        ...

      - name: cdk bootstrap
        uses: tj-actions/aws-cdk@v3
        with:
          cdk_subcommand: "bootstrap"
          cdk_stack: "stack1"
        env:
          AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}
          AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          AWS_DEFAULT_REGION: "us-east-1"

      - name: cdk diff
        uses: tj-actions/aws-cdk@v3
        with:
          cdk_subcommand: "diff"
          cdk_stack: "stack1"
        env:
          AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}
          AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          AWS_DEFAULT_REGION: "us-east-1"

      - name: cdk synth
        uses: tj-actions/aws-cdk@v3
        with:
          cdk_subcommand: "synth"
          cdk_stack: "stack1"
        env:
          AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}
          AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          AWS_DEFAULT_REGION: "us-east-1"

      - name: cdk deploy
        uses: tj-actions/aws-cdk@v3
        with:
          cdk_subcommand: "deploy"
          cdk_stack: "stack1"
          cdk_extra_args: "--require-approval never"
        env:
          AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}
          AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          AWS_DEFAULT_REGION: "us-east-1"
```

## Inputs

<!-- AUTO-DOC-INPUT:START - Do not remove or modify this section -->

|     INPUT      |  TYPE  | REQUIRED |  DEFAULT   |            DESCRIPTION             |
|----------------|--------|----------|------------|------------------------------------|
| cdk\_extra\_args | string | false    |            | AWS CDK subcommand arguments.      |
| cdk\_stack      | string | false    | `"*"`      | AWS CDK stack name to<br>execute.  |
| cdk\_subcommand | string | true     |            | AWS CDK subcommand to execute.<br> |
| cdk\_version    | string | false    | `"latest"` | AWS CDK version to install.<br>    |
| working\_dir    | string | false    | `"."`      | AWS CDK working directory.         |

<!-- AUTO-DOC-INPUT:END -->

*   Free software: [MIT license](LICENSE)

If you feel generous and want to show some extra appreciation:

[![Buy me a coffee][buymeacoffee-shield]][buymeacoffee]

[buymeacoffee]: https://www.buymeacoffee.com/jackton1

[buymeacoffee-shield]: https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png

## Credits

This package was created with [Cookiecutter](https://github.com/cookiecutter/cookiecutter) using [cookiecutter-action](https://github.com/tj-actions/cookiecutter-action)

## Report Bugs

Report bugs at https://github.com/tj-actions/aws-cdk/issues.

If you are reporting a bug, please include:

*   Your operating system name and version.
*   Any details about your workflow that might be helpful in troubleshooting.
*   Detailed steps to reproduce the bug.
