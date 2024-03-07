[![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge\&logo=ubuntu\&logoColor=white)](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions#jobsjob_idruns-on)
[![Mac OS](https://img.shields.io/badge/mac%20os-000000?style=for-the-badge\&logo=macos\&logoColor=F0F0F0)](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions#jobsjob_idruns-on)
[![Windows](https://img.shields.io/badge/Windows-0078D6?style=for-the-badge\&logo=windows\&logoColor=white)](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions#jobsjob_idruns-on)
[![Public workflows that use this action.](https://img.shields.io/endpoint?style=for-the-badge\&url=https%3A%2F%2Fused-by.vercel.app%2Fapi%2Fgithub-actions%2Fused-by%3Faction%3Dtj-actions%2Faws-cdk%26badge%3Dtrue)](https://github.com/search?o=desc\&q=tj-actions+aws-cdk+language%3AYAML\&s=\&type=Code)

[![CI](https://github.com/tj-actions/aws-cdk/workflows/CI/badge.svg)](https://github.com/tj-actions/aws-cdk/actions?query=workflow%3ACI)
[![Update release version.](https://github.com/tj-actions/aws-cdk/workflows/Update%20release%20version./badge.svg)](https://github.com/tj-actions/aws-cdk/actions?query=workflow%3A%22Update+release+version.%22)

<!-- ALL-CONTRIBUTORS-BADGE:START - Do not remove or modify this section -->

[![All Contributors](https://img.shields.io/badge/all_contributors-1-orange.svg?style=flat-square)](#contributors-)

<!-- ALL-CONTRIBUTORS-BADGE:END -->

## aws-cdk

Run [aws cdk](https://docs.aws.amazon.com/cdk/v2/guide/getting_started.html) commands.

## Features

*   Run [aws-cdk](https://docs.aws.amazon.com/cdk/v2/guide/getting_started.html) with support for downloading the package or running a pre-installed version. (Note: This requires passing the correct value for the `working_dir` input).
*   Waits for pending stack `UPDATE_COMPLETE` before running new deployments.

## Usage

```yaml
...
    steps:
      - uses: actions/checkout@v4
        ...
     
      - name: Install dependencies
        ...

      - name: cdk bootstrap
        uses: tj-actions/aws-cdk@v4
        with:
          cdk_subcommand: "bootstrap"
          cdk_stack: "stack1"
        env:
          AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}
          AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          AWS_DEFAULT_REGION: "us-east-1"

      - name: cdk diff
        uses: tj-actions/aws-cdk@v4
        with:
          cdk_subcommand: "diff"
          cdk_stack: "stack1"
        env:
          AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}
          AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          AWS_DEFAULT_REGION: "us-east-1"

      - name: cdk synth
        uses: tj-actions/aws-cdk@v4
        with:
          cdk_subcommand: "synth"
          cdk_stack: "stack1"
        env:
          AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}
          AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          AWS_DEFAULT_REGION: "us-east-1"

      - name: cdk deploy
        uses: tj-actions/aws-cdk@v4
        with:
          cdk_subcommand: "deploy"
          cdk_stack: "stack1"
          cdk_extra_args: >-
            --progress events
            --require-approval never
            --parameters environment=${{ secrets.ENVIRONMENT }}
        env:
          AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}
          AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          AWS_DEFAULT_REGION: "us-east-1"
```

## Inputs

<!-- AUTO-DOC-INPUT:START - Do not remove or modify this section -->

|                                   INPUT                                    |  TYPE  | REQUIRED |  DEFAULT   |             DESCRIPTION             |
|----------------------------------------------------------------------------|--------|----------|------------|-------------------------------------|
| <a name="input_cdk_extra_args"></a>[cdk\_extra\_args](#input_cdk_extra_args) | string |  false   |            |    AWS CDK subcommand arguments.    |
|        <a name="input_cdk_stack"></a>[cdk\_stack](#input_cdk_stack)         | string |  false   |   `"*"`    | AWS CDK stack name to <br>execute.  |
| <a name="input_cdk_subcommand"></a>[cdk\_subcommand](#input_cdk_subcommand) | string |   true   |            |   AWS CDK subcommand to execute.    |
|     <a name="input_cdk_version"></a>[cdk\_version](#input_cdk_version)      | string |  false   | `"latest"` |     AWS CDK version to install.     |
|     <a name="input_working_dir"></a>[working\_dir](#input_working_dir)      | string |  false   |   `"."`    |         Working directory.          |

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

## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->

<!-- prettier-ignore-start -->

<!-- markdownlint-disable -->

<table>
  <tbody>
    <tr>
      <td align="center" valign="top" width="14.28%"><a href="https://home.boidol.dev/"><img src="https://avatars.githubusercontent.com/u/652404?v=4?s=100" width="100px;" alt="Raphael Boidol"/><br /><sub><b>Raphael Boidol</b></sub></a><br /><a href="https://github.com/tj-actions/aws-cdk/commits?author=boidolr" title="Documentation">📖</a></td>
    </tr>
  </tbody>
</table>

<!-- markdownlint-restore -->

<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!
