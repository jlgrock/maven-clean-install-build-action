# Title

This runs standard maven build installs with standard flags used by the IKMDev team.

## How to Use

Create a build in the `.github/workflows` folder, as described in the 
[GitHub Documentation](https://docs.github.com/en/actions/writing-workflows/quickstart).  Add the following code, 
or something like it:

```yaml
env:
  MAVEN_SETTING: '/home/ec2-user/maven/.m2/settings.xml'
  BRANCH_NAME: ${{github.ref_name}}

jobs:
  build-job:
    name: Build Job
    runs-on: self-hosted
    if: github.repository_owner == 'ikmdev'
    steps:
          - name: Build IKMDEV Code
            uses: ikmdev/ikmdev-build-action@main
            with:
              branch_name: ${{env.BRANCH_NAME}}
```

## Issues and Contributions

Technical and non-technical issues can be reported to the GitHub Issue Tracker.

Contributions can be submitted via pull requests. Please check the [contribution guide](doc/how-to-contribute.md) for more details.
