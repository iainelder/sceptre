# CHANGELOG

Categories: Added, Removed, Changed, Fixed, Nonfunctional, Deprecated

## Unreleased

## 4.5.3 (2025.03.27)
- [Resolve #1517] Updated the Cloudformation Hook logging message
- [resolves #1514] Update docs for docker repo (#1515)
- [Resolve #1520] Replace hard-coded shell paths (#1523)
- [Resolve #1539] Drop Python 3.8 support (#1540)
- [Resolves #1541] Update deepdiff to support numpy2.0 (#1542)

## 4.5.2 (2024.08.31)

### Fixed
 - [Resolve #1506] Remove unused __eq__ method

## 4.5.1 (2024.08.29)

### Fixed
 - [Resolve #1503] Dependency conflict with packaging

## 4.5.0 (2024.08.28)

### Added
 - [Resolve #915] Support ChangeSetType CREATE (#1469)
 - [Resolves #1187] Add configuration for inheritance strategies for list and dict configs (#1445)
 - [Resolve #1443] Add parameter type checking (#1442)

#### Changed
 - [Resolve #1498] Tweak diff output (#1499)
 - [Resolve #1446] Print edges in cyclical dependency (#1447)

### Fixed
 - [Resolve #1493] Complete DisableRollback implementation
 - [Resolve #723] Fix update command with change sets for multiple stacks (#1480)
 - [Resolve #1483] Handle errors in change sets (#1486)
 - [Resolve #1484] Gracefully handle invalid parameters (#1485)
 - [Resolves #1268] Modify ConfigFileNotFound Error to Conditionally Include Valid Stack Paths (#1270)
 - [Resolve #1451] Stop suppressing ClientError in describe_outputs (#1452)
 - [Resolve #1468] Cast parameters to strings (#1471)
 - [Resolve #937] Reset Jinja2 variable cache between config files (#1472)
 - [Resolves #1460] Update `NO_ECHO_REPLACEMENT` (#1461)
 - [Resolves #1388] Handle failures gracefully in stack outputs (#1391)
 - [Resolve #1436] Handle exception in differ (#1437)

### Nonfunctional
 - [Resolve #1478] Update to latest packaging
 - [Resolves #841] Add documented entry for ASG hook (#1374)
 - chore: remove github workflow (#1479)
 - A minor clarification to the docs on running integration tests (#1475)
 - Fix release workflow: GH actions uses globs instead of regex
 - Fix integration test workflow (#1439)
 - Remove classifiers (#1438)
 - Remove removed_in version of deprecated settings (#1423)
 - CI: add comments to GH workflows
 - stop duplicate gate workflow runs (#1433)
 - run gate workflow on branch creation
 - Update CI and doc
 - CI: add integration test workflow (#1430)
 - Disable concurrent integration test runs (#1426)
 - Refactor GH workflows (#1416)
 - CI: Remove install dependencies (#1428)
 - reconfigure pre-commit validation (#1427)
 - Remove an external resolver integration test (#1425)
 - Generate github test matrix from tox (#1422)
 - CI: fix github event reference (#1424)
 - Fix integration tests (#1420)
 - ci: fix docker release dependency
 - pypi release should run in parallel to docker release
 - update docker push workflow
 - fix ci: add user/app to docker tags deployments
 - fix deployment to dockerhub (#1415)
 - ci: attempt unit test fix (#1414)
 - [Resolves #1401] Move CI to github actions (#1412)
 - ci: install poetry dependencies
 - ci: install poetry
 - another tag regex fix
 - fix tag regex for ci
 - fix ci: GH action file needs to be in workflows folder
 - bootstrap GH action CI (#1413)
 - [Resolves #1327] Remove docs build and publish (#1407)

## 4.4.2 (2024.01.13)
 - Add support for python 3.12 (#1390)
 - Drop support for Python 3.7 (#1382)
 - [Resolves #1327] Setup readthedocs (#1404)
 - [Resolves #1377] Remove auto announcements to twitter (#1385)
 - [Resolves #1383] Simplify stderr test for cmd hook (#1387)
 - Remove project Makefile (#1403)
 - docs: Update instructions to generate docs and remove requirements file for docs (#1398) (#1405)
 - ci: use matrix for unit tests (#1395)

## 4.3.0 (2023.10.07)
 - [Resolve #1351] Add debugging to Jinja rendering (#1375)
 - [Resolves #1356] Add export=stackoutput and stackoutputexternal feature to list outputs (#1357)
 - [Resolves #1213] Add shell option to cmd hook (#1372)
 - [Resolve #1370] Use Python 3.11 for Black (#1371)
 - Documentation updates (#1355) (#1373)

## 4.2.2 (2023.07.18)
 - [Resolve #1358] Updating PyYaml to ^6.0 (#1359)

## 4.2.1 (2023.06.14)
 - [Resolve #1344] Addressing issue with Generate hook and its deprecation (#1346)
   Here is what this includes:
     * The `dump_template` action ALSO triggers `before_generate` and
       `after_generate`
     * The `generate` action ALSO triggers `before_dump_template` and
       `after_dump_template`
     * The StackDiffer invokes `dump_template` rather than `generate`, preventing
       our own code from triggering deprecation warnings.
     * The documentation for hook points is updated to include all current hooks,
       including notes about the aliasing.
     * Deprecation of `generate` is removed after discussion in Slack. This
       deprecation would be too disruptive to many users, and we agreed instead
       to support a permanent alias of `generate` => `dump_template`.

## 4.2.0 (2023.05.25)

 - [Resolves #894] Switch to using poetry (#1323)
 - Remove Moto dependency (#1330)
 - Write rendered template to a temp file (#1321)
 - [Resolve #1319] Add colouring for missing state DELETE_SKIPPED
 - [Resolve #1291] Fix attribute error caused by a relative project path
 - [Resolve #1318] Implement dump template and write output files
 - [Resolve #1336] Add bugfix in Stack Differ (#1337)

## 4.1.0 (2023.04.17)
### Added
 - [Resolve #1304] Adding StackLoggerAdapter to hooks, resolvers, and template handler
 - [Resolve #1263] Stack output caching
 - [Resolve #1252] Supporting resolvers in Hook and Resolver arguments, with new
   !substitute, !join, !split, and !select resolvers!

### Nonfunctional
 - add a pre-commit linter to validate circleci configs

## 4.0.2 (2023.02.20)
### Fixed
 - [Resolve #1307] Fixing Connection Manager bug (#1308)

## 4.0.1 (2023.02.12)

### Changed
 - Supporting `!rcmd` resolver up to v2

## 4.0.0 (2023.02.08)

### Added
 - [Resolve #1283] Introducing `sceptre_role`, `cloudformation_service_role` (#1295)
   - These are just iam_role and role_arn renamed to be a lot clearer. See "Deprecations" below.


### Changed
 - [Resolve #1299] Making the ConnectionManager a more "friendly" interface for hooks, resolvers,
   and template handlers (#1287, #1300)
   - This creates adds the public `get_session()` and
     `create_session_environment_variables()` methods to make AWS interactions
     easier and more consistent with individual stack configurations for
     iam_role, profile, and region configurations.
   - The `call()` method now properly distinguishes between default stack
     configurations for profile, region, and `sceptre_role` and setting those to
     `None` to nullify them.
 - Preventing Duplicate Deprecation Warnings from being emitted (#1297)

#### _Potentially_ Breaking Changes
 - The !cmd hook now invokes the passed command using the AWS environment
   variables that correspond with the stack's IAM configurations (i.e. iam_role,
   profile, region). This means that the hook will operate the same as every
   other part of Sceptre and regard how the stack is configured. This should make
   it easier to invoke other tools like AWS CLI with your hooks. However, if
   your project is setting environment variables with the intent to change how
   the command authenticates with AWS (such as a different token, profile, or
   region), these environment variables will be overridden. To maintain the same
   functionality, you should prefix your command with
   `export AWS_SESSION_TOKEN={{environment_variable.AWS_SESSION_TOKEN}} &&` (or
   whatever other environment variable(s) you need to explicitly set).

### Deprecations
 - [Resolve #1283] Deprecating `iam_role`, `role_arn`, and `template_path` (#1295)
   - `iam_role` and `role_arn` have been aliased to `sceptre_role` and
      `cloudformation_service_role`. Using these fields will result in a
      DeprecationWarning.
   - `template_path` has actually been slated for removal since v2.7. `template`
      should be used instead. Using `template_path` will result in a
      DeprecationWarning.
   - All three deprecated StackConfig fields will be removed in v5.0.0.

## 3.3.0 (2023.02.06)

### Added
 - [Resolve #1261] Add coloured differ (#1260)
   - Implements coloured diffs for the diff (difflib) command. Responds to --no-color.
 - [Resolves #1271] Extend stack colourer to include "IMPORT" states (#1272)
 - [Resolves #1179] cloudformation disable-rollback option (#1282)
   - Allow user to disable a cloudformation rollback on a sceptre deployment.

### Changed
 - [Resolve #1098] Deploy docker container to sceptreorg repo (#1265)
   - Deploy sceptre docker images to dockerhub sceptreorg repo instead of cloudreach repo
 - Updating Setuptools and wheel versions to avert security issues
 - [Resolve #1293] Improve the Stack Config Jinja Syntax Error Message to include the Stack Name (#1294)
 - [Resolves #1267] Improve the Stack Config Jinja Error Message to include the Stack Name (#1269)

### Fixed
 - [Resolve #1273] Events start from response time (#1275)
   - Resolves #1273 by starting event filtering from the timestamp returned in
     the AWS response headers rather than relying on the workstation clock.
 - [Resolve #1253] Failed downloads raise error (#1277)
   - Throwing an informative error when the template fails to download instead
     of passing the error message to CloudFormation.
 - [Resolves #1179] Changed disable-rollback default to None (#1288)
   - We want the default value to be None to represent "Do whatever's configured
     in the StackConfig" and True/False will override the StackConfig.

### Nonfunctional
 - Add tweet-release to CircleCI config (#1259)
 - [Resolves #1276] Adopt Black Auto-formatter (#1278)
   - Reformatting all Python files using the Black code formatter. This also
     delivers a new function for generating `__repr__` methods which was needed
     to deal with a line-too-long issue in Template. Per discussion in #1276 this
     PR also disables E203 in flake8.
 - Update sceptre-circleci docker image (#1284)
   - Update to build and test with a docker image that's based on the official
     circleci python docker image.
 - [Resolve #1264] Updating the CDK docs to point to the new sceptre-cdk-handler
   (#1285)
   - This updates our docs to no longer reference the old CDK approach (which
     didn't work with CDK assets). In its place, it references the new
     sceptre-cdk-handler package that covers that functionality.

## 3.2.0 (2022.09.20)

### Added
 - [Resolve #1225] Added Python 3.10 support (#1227)
 - Implemented a `sceptre dump config` command (#1220)
 - [Resolve #1224] Add --drifted option to `drift show` command (#1246)
 - [Resolve #1212] Conditional Stacks via "ignore" and "obsolete";
   `sceptre prune` command for cleaning up obsolete stacks (#1229)

### Changed
 - [Resolve #1225] Updating `troposphere` version for python 3.10 compatibility (#1226)
 - [Resolve #1225] Updating Sceptre to use importlib on Python 3.10 (#1240)

### Fixed
 - [Resolve #1218] Fixing false-diff reports when parameters end with linebreaks (#1219)
 - [Resolve #1236] Updating `networkx` to miticate CWE-502 (#1243)
 - [Resolve #1245] Updating `setuptools` version to address build failure (#1247)
 - [Resolve #1234] Bugfix to support empty var files (#1248)
 - [Resolve #1223] Fix crash when resolvers return lists of `None` (#1249)

### Nonfunctional
 - Added sponsors section to CONTRIBUTING.md (#1221)
 - Made unit tests run in parallel when running `make test-all` (#1231)
 - Removing awscli from CircleCI builds (#1232)
 - Updated sceptre-circleci docker image for Python 3.10 support (#1230)
 - Using CircleCI cache to speed up builds (#1242)

## 3.1.0 (2022.04.13)

### Added
 - [Resolve #1080] Added duration_seconds parameter to adopt DurationSeconds in boto (#1210)

### Changed
 - [Resolve #1203] Updating packaging requirement (#1211)

## 3.0.0 (2022.02.22)

### Breaking Changes
 - Python 3.6 support has been removed due to that version reaching end-of-life status
 - Jinja2 has been upgraded to v3.0

### Added
 - [Resolve #1114,#426] Resolvable stack_tags (#1184)
 - [Resolve #1114,#886,#491] Resolvable role_arn and template_bucket_name (#1153)
 - [Resolve #1114] Resolvable iam_role (#1188)
 - [Resolve #1114] Resolvable Template Handler configs and the !stack_attr resolver
 - [Resolve #1167] Add list stacks command (#1168)
 - [Resolve #1169] Add drift detect and drift show commands (#1170)

### Removed
 - [Resolves #1201] Remove Py3.6 support (#1206)

### Changed
 - [Resolve #1114,#1000] Placeholders for non-deployed stacks in non-deployment commands (#1185)

### Fixed
 - [Resolves #1201] Fix dependency conflicts (Jinja2, moto) (#1206)

### Nonfunctional
- [Resolves #1194] Docs: "know"->"knows" (#1195)
- docs: fix template path in getting-started (#1198)
- Fix spelling of stack_group_config (#1199)

## 2.7.1 (2021.12.06)

### Fixed

- [Resolve #1175] Adding commas for cfn-flip dependency (#1176)
- [Partially resolves #1174] Fixing Docs deployment by pinning Sphinx to lesser version (#1171)

### Nonfunctional

- Fix typo in CDK doc (#1181)
- Add release instructions (#1162)
- Resolve #1163 update doc link to new domain (#1166)
- Pointing SAM docs toward the sceptre-sam-handler (#1164)

## 2.7.0 (2021.11.18)

### Added

- [Resolve #966] Add support for J2 Environment configuration
- [Resolves #919] Add merge_keys option (#928)
- [Resolves #1064] Add feature list change-set --url (#1065)
- [Resolves #213] Add support for template handlers  (#1088)
- [Resolves #1106] S3 template handler jinja and python support (#1110)
- [Resolves #1124] http template handler (#1125)
- Set file as the default template handler type (#1127)
- Add retry and timeout to http template handler (#1145)
- [Resolve # 683] Introducing the Diff Command (#1132)

### Fixed

- [Resolves #813] Fix recursive config render (#1083)
- [Resolve #1096] Gracefully executing SAM Change sets (#1099)
- [Resolves 556] fix incorrect stack_output_external examples (#1109)
- [RESOLVE #946] Fixing bug preventing StackGroup dependencies (#1116)
- [Resolve #1138] Bugfix for j2_environments (#1137)
- [Resolve #1135] Fix path to templates (#1141)
- [Resolve #1143] fix "create" cmd with existing stack (#1144)
- [Resolves #1148] Correct path logic (#1149)

### Nonfunctional

- [Resolves #582] update imp to importlib (#1092)
- [Resolves #1090] Install troposphere as an extra package (#1104)
- [Resolves #1087] Add YAML document markers to template body (#1089)
- Stop hiding critical debug info in helpers (#988) (#997)
- [Resolves #1139] Provide useful info on invalid jinja file (#1142)

## 2.6.3 (2021.08.13)

### Fixed

- [Resolves #1078] Fix delete CLI dependency tree

## 2.6.2 (2021.08.02)

### Fixed

- [Resolves #1072] fix sceptre install for docker

## 2.6.1 (2021.07.30)

### Fixed

- Fix dependencies to install sceptre-file-resolver
- Consolidate pip requirements files

## 2.6.0 (2021.07.29)

### Added

- Doc: added docs to release workflow in .circleci/README.md
- Introduce an .editorconfig to sync common editor configuration across developer systems
- Update click version
- Update docker container to use Python 3.7
- Make the sceptre-resolver-cmd resolver a core resolver
- Make the sceptre-file-resolver a core resolver

### Removed

- Doc: Removed V1 docs

### Fixed

- [Resolves #1013] Fix virtual-hosted-style uri
- Remove unnecessary padding with sceptre output command
- Do not open a web browser during test
- Optimize Sceptre Start Time by only Processing Dependent Configuration Files
- [Resolves #1042] Fix OS path resolution on windows

## 2.5.0 (2021.05.01)

### Added

- Added support for python 3.8 & 3.9
- Support PEP-518 builds with pyproject.toml file
- Support before_create_change_set and after_create_change_set hooks
- Allow generate command to run hooks

### Removed

- Removed support for python 2.7 & 3.5

### Fixed

- Fix "sceptre list outpuuts" command
- Provide more info on config parsing errors

### Nonfunctional

- Removed Sonarqube
- Setup pre-commit linters and hooks
- General documentation updates

## 2.4.0 (2020.10.03)

### Added

- Support for hooks on create_change_set

### Fixed

- Selection of correct stack group based on exact name
- Execution of empty change sets

### Nonfunctional

- Added jinja example to documentation
- Fixed documentation typos
- Tidied documentation by removing unnecessary comments
- Remove documented support for Python 2.7

## 2.3.0 (2020.02.03)

### Added

- `iam_role` capability for `stack-config`
- Support for complex data for `resolvers` and `hooks`
- Hooks support for `launch` command

### Fixed

- Replace JSON with YAML as default Cloudformation format in documentation
- Broken cross-page references in documentation
- Jinja autoescape vulnerability
- Connection manager imports
- `rel_paths` for `_call_sceptre_handler` in `template.py`
- Linting as a side-effect of upgrading flake package

### Nonfunctional

- Add documentation clean target
- Clean up code blocks in documentation
- Clarify pip vs. Docker installation in documentation
- Fix documentation version links
- Add autocomplete doc for ZSH shell
- Update integration test instructions
- Allow to keep specific versions of documentation
- Keep version `1.3.4` and `1.4.2` active on github pages
- Fix formatting error in `terminology.rst`
- Upgrade Dockerfile to Alpine 3.10
- Improve error message for `stack_output` dependencies
- Improve `sceptre generate` formatting
- Unpinned some requirements to avoid conflict with other packages

## 2.2.1 (2019.08.19)

### Fixed

- `typing` install dependency for Python version < 3.5
- Race condition in stacks causing RecurrsiveGet exception

## 2.2.0 (2019.08.16)

### Added

- Meaningful Jinja Template exception output handling

### Fixed

- Recursion in `sceptre_user_data` becoming infinite
- AWS `rate_exceeded` error when hitting AWS API too frequently
- Readme links
- StackGraph debugging output

### Nonfunctional

- Moved CircleCI Dockerfile to its own repository
- Add SonarQube analysis
- Change CircleCI setup to use context over environment variables
- Removed redundant test code
- Add badges to README
- Adjust Coverage fail-level to 92%
- Update CONTRIBUTING Guide

## 2.1.5 (2019.06.28)

### Fixed

- Fix missing `Fn::Split` from CFN Functions in cli `generate`
- Fix Docker deploy latest image
- Fix setup.py supported programming language
- Fix CircleCI docs deploy to allow empty commits
- Fix CircleCI workflow to add docker build to tagged docker deployments

### Nonfunctional

- Fix README git conflict issues
- Add DockerHub repo link in README

## 2.1.4 (2019.06.26)

### Fixed

- CLI to use correct JSON formatting as default
- `sceptre generate` for non-trivial JSON and YAML
- Support for nested dicts in CLI `--var` flag
- Error handling for missing AWS credentials
- `stack_output` resolver windows path
- Stack update error hadnling
- Overwritten `project_code` in `stack_output` dependencies
- Typo in terminology documentation

### Nonfunctional

- Add Official Docker image and automatic DockerHub releases
- Change target git repository to deploy docs
- Officially support Python 3.7
- Update README documentation links

## 2.1.3 (2019.05.14)

### Fixed

- Fix `stack_name` for s3 upload in Windows environment.

## 2.1.2 (2019.05.09)

### Fixed

- Fix `stack_output` resolver recursion error.

## 2.1.1 (2019.05.01)

### Fixed

- Fix CLI list output export issue.

- Fix path separators between operating systems.

- Fix S3 uploads to support China regions.

### Nonfunctional

- Upgrade to PyYaml 5.1.

- Update custom hook docs.

- Improve documentation site.

## 2.1.0 (2019.03.01)

### Added

- Support for SAM templates.

- Improve handling of missing config attributes.

### Nonfunctional

- Update colorama dependency version.

- Fix circleci build

## 2.0.3 (2019.02.15)

### Fixed

- Fix ConfigReader to follow symbolic links.

- Fix output of `--output yaml` with Python objects.

- Fix CLI `update change-set` command.

### Nonfunctional

- Improve Documentation.

- Fix Migration Guide documentation on `tags` vs `stack_tags`.

- Improve formatting of CLI `--help` command.

- Update `six` dependency version.

## 2.0.2 (2019.01.10)

### Fixed

- Fix `write` method in `sceptre.cli.helpers` to better handle `yaml` and `json`
  output format.

- Fix `sceptre generate` in CLI so that it respects `--output` flag.

- Update `PyYaml` dependency version to fix `CVE-2017-18342`.

- Fix `--export` option for `sceptre list outputs` for setting environment
  variables.

### Nonfunctional

- Improve `sceptre.stack.Stack.__repr__()` so that objects and lists are not
  contained in strings.

- Remove duplicate timestamp from logging in `plan.actions`.

- Fix minor documentation typo in `stack_group_config.md` stack example.

- Remove redundant `status` self-assignment in `sceptre.plan.actions.launch()`

## 2.0.1 (2018.12.17)

### Fixed

- Fix `list` and `describe` cli output

- Fix circleci and Makefile config

- Fix accessing `command_path` as list in templates

- Fix adding implicit dependencies for `stack_output` resolver

### Nonfunctional

- Improve delete stack confirmation message

- Improve delete change set message

- Add newline in `cli.md` docs to format code block correctly

- Update docs for Custom Resolver `setup.py`

- Update Custom Resolver docs

- Clarify docs on stack_output resolver

## 2.0.0 (2018.11.30)

### Added

- Support for `stack_group_config` via the `Stack()` API.

- Support for accessing `stack_group_config` in Templates

- `--ignore-dependencies` flag to CLI and API.

### Removed

- `write()` from `sceptre.config.graph.StackGraph`

### Fixed

- Describe commands output formatting

- Website Page titles

### Nonfunctional

- Updated Project docs

- Updated Website Documentation

- Removed unnecessary string from CLI output

## 2.0.0rc1-2 (2018.11.22)

### Fixed

- Added missing `stack_group_config` attributes to Stack.

## 2.0rc1 (2018.11.21)

### Added

- StackGraph (5171ae0)

- SceptreContext (c17cfc5)

- SceptrePlan (ab38157)

- SceptrePlanExecutor (ab38157)

- Support for cross-StackGroup dependencies (0b104db)

- StackActions (e8e34e8)

### Removed

- Environments. Stacks & their relationships are now held in StackGraph
  (0b104db)

### Changed

- Config.yaml `template_path` attribute. By default Sceptre uses "templates" as
  the root directory for `template_path` so the user should not specify
  `templates/` as part of the `template_path` attribute (0b104db)

- Update docstrings (0b104db)

- Stack class. The functions available to Stacks are stored in StackActions
  (0b104db)

### Nonfunctional

- Updated project documentation such as README (0b104db)
- Changed project cocs to use Markdown format (README, CHANGELOG, CONTRIBUTING)
  (0b104db)

## 1.4.2 (2018.09.11)

- Fix Config dict merge strategy returning None

## 1.4.1 (2018.08.22)

- Fix KeyError when merging configs

## 1.4.0 (2018.08.02)

- Update Click and PyYaml dependency versions
- Improve delete-change-set output message
- Add stack configuration merging strategies
- Add AMI Resolver to contrib/
- Fix launch environment dependency path
- Add error message for non-leaf environments
- Add KMS resolver to contrib
- SSM resolver to contrib
- Improve error handling in CLI and StackOutput
- Amend linting for integration tests and docs
- Decrease the number of circleci parallel runs
- Update Jinja dependency version to `<=2.8`
- Add ".template" as allowed file extensions for templates
- Add bash-completion script to contrib
- Add a contrib directory for non-core community contributions
- Update docs Makefile
- Add HTML title header and icon to docs

## 1.3.4 (2018-02-19)

- Fixed CircleCi PyPi Deployment
- Update Boto3 requirements

##1.3.3 (2018-02-19)

- Released in Error. Contained breaking changes from v2. Fixed in 1.3.4.

## 1.3.2 (2017.11.28)

- Improving stack dependency resolution.
- Improving CLI output for validate template command.
- Consolidating pip requirements files.
- Fixing Python 3 support.
- Fixing documentation typos.

## 1.3.1 (2017.10.23)

- Removing sceptre diff command.
- Adding support for the stack notifications attribute in stack config.
- Fixing bug which caused session re-creation on every boto call.

## 1.3.0 (2017.10.16)

- Re-adding the ability to specify credential profile in the environment config.
- Adding init project command to help initialize a new Sceptre project.
- Adding init env command to help initialize a new Environment config.
- Adding diff command to display differences between the local and deployed
  stack template.
- Fixed error message displayed for empty environments.
- Adding `environment_config` to config template rendering.
- Adding `on_failure` parameter to stack config.
- Adding automatic renewal of expired credentials when assuming IAM Roles.
- Deprecating use of `bash` hook in favour of `cmd` hook.
- Deprecating use of `asg_scheduled_actions` hook in favour of
  `asg_scaling_processes` hook.
- Adding status colouring for output of describe-env command.
- Fix spelling mistakes in documentation.

## 1.2.1 (2017.7.21)

- Changing Jinja rendering for templates only with '.j2' extension.
- Fixing broken links in documentation website.
- Updating references to Python templates instead of Troposphere templates.

## 1.2.0 (2017.7.14)

- Increasing maximum number of boto call retires from 5 to 30.
- Adding support Jinja rendering for stack templates.
- Adding stricter requirements for existing stack state when launch
  environments.
- Adding `cmd` hook for better cross platform support.
- Adding documentation around architecture of Sceptre projects.
- Adding versioned documentation.
- Improving documentation formatting.
- Fixing path error bug when using environment level commands on Windows.
- Fixing bug to correctly throw an AtrributeError in a Python stack template.

## 1.1.2 (2017.5.26)

- Fixing bug for `protect` in stack config.

## 1.1.1 (2017.2.29)

- Respect --dir when loading custom resolvers and hooks.

## 1.1.0 (2017.3.3)

- Include Scope in `update-stack-cs` output.
- Updates to documentation.

## 1.0.0 (2017.1.31)

- Removing deprecation notices.
- Updating documentation.

## 0.50.0 (2017.1.24)

- Changing syntax used for resolvers and hooks in config files.
- Deprecating use of `sceptre_get_template` function in Troposphere templates.
- Deprecating the accessing of Troposphere templates returned from
  `sceptre_get_template`.
- Deprecating the accessing of Troposphere templates from the global variable
  `t`.
- Deprecating the global variable `SCEPTRE_USER_DATA`.
- Adding support for `sceptre_handler` function in Troposphere templates.
- Adding support for pure CloudFormation JSON strings returned by
  `sceptre_handler`.
- Adding support for `sceptre_user_data` passed to `sceptre_handler`.
- Fixing bug in update-stack-cs.
- Adding project-variables resolver.

## 0.49.1 (2017.1.6)

- Adding documentation for CloudFormation Service Role.

## 0.49.0 (2017.1.6)

- Updating documentation on hooks.
- Adding support for CloudFormation Service Role.
- Adding support for custom stack names.
- Removing (before|after)\_launch hook.
- Changing documentation styling.
- Adding Python 3 support.
- Adding --verbose argument to describe-change-set.
- Adding support for launching stacks without uploading the template to S3.
- Adding a FAQ section on `parameters` vs `sceptre_user_data`.
- Adding support for CloudFormation template written in YAML.
- Bumping boto3 requirement.
- Adding more intuitive delete stack message.
- Removing profile.
- Fixing a multithreading bug.
- Improve CLI UX by printing only an exception's message, not the whole stack
  trace.
- Adding environment path check.
- Refactoring out code that fetches stack status.

## 0.48.0 (2016.12.5)

- Fixing StackStatusColourer: UPDATE_FAILED wan't coloured.
- Fixing bug from uploading templates to S3 from Windows.
- Improving exception thrown when a user tries to use the stack output resolve
  on a stack with no outputs.

## 0.47.0 (2016.12.1)

- Launch now deletes stacks in the CREATE_FAILED or ROLLBACK_COMPLETE states
  before re-creating them.
- Adding support for Troposphere<1.10.0.

## 0.46.0 (2016.11.11)

- Adding support for multiple environments.
- Speeding up integration tests.
- Switching to CircleCI for continuous integration and deployment of
  documentation.
- Changing template S3 key to use a UTC timestamp rather than seconds since
  epoch.
- Changing update-stack-cs to delete the change set by default.
- Stopping appending region to template bucket name.
- Refactoring logger.
- Changing exception names from <Name>Exception to <Name>Error.
- Publishing development docs to http://sceptre-dev.ce-tools.cloudreach.com/.

## 0.45.0 (2016.08.25)

- Adding support for Troposphere 1.8.
- Adding stack protection support.
- Adding support for allowing Troposphere templates to import modules from
  parent directories.
- Adding documentation section for IAM role setup.
- Fixing bug in update-wth-cs command.

## 0.44.0 (2016.08.5)

- Adding require_version.
- Renaming --machine-readable to --output.
- Refactoring hook.py.

## 0.43.4 (2016.08.2)

- Improving logging.

## 0.43.3 (2016.08.2)

- Updating CONTRIBUTING.rst.

## 0.43.2 (2016.08.1)

- Fixing multithreaded S3 bucket create bug.

## 0.43.1 (2016.08.1)

- Deprecating the CLI flags --iam-role, --profile, --region.

## 0.43.0 (2016.08.1)

- Adding machine readable output support.

## 0.42.0 (2016.08.1)

- Adding support for CAPABILITY_NAMED_IAM.

## 0.41.0 (2016.07.28)

- Adding Resolver support for sceptre_user_data.

## 0.40.0 (2016.07.28)

- Adding plugin support for Parameter Resolvers and Hooks.

## 0.39.2 (2016.07.21)

- Fixing exit status bug.

## 0.39.1 (2016.07.15)

- Updating requirements.

## 0.39.0 (2016.07.15)

- Add sceptre_hooks.
- Add builtin suspend and resume asg scaling actions.

## 0.38.4 (2016.07.14)

- Adding deprecation warning for --profile, --region, --iam_role.

## 0.38.3 (2016.07.14)

- Combining account_id and iam_role into a single parameter, iam_role, which is
  now the ARN of the IAM Role to assume.
- Fixing bug in integration tests.

## 0.38.2 (2016.07.14)

- Updating docs.

## 0.38.1 (2016.07.14)

- Updating docstrings.

## 0.38.0 (2016.07.14)

- Removing autocomplete as it broke integration tests.
- Fixing integration tests.

## 0.37.0 (2016.07.13)

- Adding the ability to tag stacks created by Sceptre.

## 0.36.0 (2016.07.12)

- Adding templating support to config files.

## 0.35.1 (2016.07.12)

- Fixing permissions on autocomplete files.

## 0.35.0 (2016.07.12)

- Sceptre now encrypts templates uploaded to S3 using AES256 by default.

## 0.34.0 (2016.07.12)

- Adding autocomplete support for bash and zsh.

## 0.33.0 (2016.07.11)

- Specify sceptre directory via --dir flag.

## 0.32.0 (2016.07.11)

- Refactoring how parameters are handled internally.
- Adding stack_output_external resolver.
- Adding the ability to explicitly specify dependencies.

## 0.31.0 (2016.07.11)

- Adding sceptre-update-cs.

## 0.30.0 (2016.07.08)

- Tail stack events for sceptre execute-change-set.
- Added formatted output for sceptre describe-change-set.

## 0.29.1 (2016.07.08)

- Fixing CI bug in 0.29.0.

## 0.29.0 (2016.07.08)

- Adding automatic support for no-colour'ed output.

## 0.28.0 (2016.07.07)

- Adding --no-colour flag.

## 0.27.2 (2016.07.07)

- Updating docs to add get-stack-policy and set-stack-policy.

## 0.27.1 (2016.07.07)

- Patching unittests and lint from previous release.

## 0.27.0 (2016.07.07)

- Adding get-stack-policy and set-stack-policy.

## 0.26.1 (2016.07.06)

- Changing ConfigReader object to Config object.

## 0.26.0 (2016.07.06)

- Adding more integration tests.

## 0.25.1 (2016.07.05)

- Fixing UnrecognisedHookTaskTypeException import in hook.py.

## 0.25.0 (2016.07.05)

- Adding describe-env command.

## 0.24.1 (2016.07.05)

- Updating documentation.

## 0.24.0 (2016.07.04)

- Ability to specify the region via the cli.
- Ability to specify a profile via the cli or config.yml.
- Ability to specify a role via the cli.
- Skip role assume when no role is specified in config.yaml or via the cli.

## 0.23.1 (2016.06.30)

- Moving upload_template_to_s3 into the Template object.

## 0.23.0 (2016.06.30)

- Adding support for the cascading of <stack_name>.yaml files.
- Moved --debug flag to be after sceptre keyword (\$ sceptre --debug <command>).
- Refactor how config is handled internally.
- Lazy load stack config and templates.

## 0.22.1 (2016.06.28)

- Adding dependency resolving to create-change-set.

## 0.22.0 (2016.06.27)

- Adding hooks.

## 0.21.2 (2016.06.24)

- Refactoring connection_manager.

## 0.21.1 (2016.06.14)

- Fixing bug in template.py.

## 0.21.0 (2016.06.14)

- Adding sceptre describe-stack-outputs command.

## 0.20.0 (2016.06.14)

- Switching from TROPOSPHERE_DATA to SCEPTRE_USER_DATA.
- Switching from configure to PyYaml.
- Fixing a print stack events error.

## 0.19.0 (2016.06.8)

- Adding Boto3 call retries when request limits are hit.

## 0.18.2 (2016.06.2)

- Removing a potential race condition when storing templates in S3.

## 0.18.1 (2016.05.27)

- Tidying up method names in the Stack() object.

## 0.18.0 (2016.05.26)

- Moving to using threading to launch/delete environments.
- Create/update/launch/delete commands now return non-zero if the command fails.

## 0.17.0 (2016.05.10)

- Adding basic integration tests.

## 0.16.1 (2016.05.9)

- Bumping to Troposphere 1.6.0.

## 0.16.0 (2016.05.4)

- Switching from Docopt to Click, improving support for use as a Python module.

## 0.15.3 (2016.04.21)

- Bumping boto3 dependency version to 1.3.1.

## 0.15.2 (2016.04.21)

- Defend against troposphere_data being a string in yaml.

## 0.15.1 (2016.04.14)

- Moving exceptions into their own file, `exceptions.py`.

## 0.15.0 (2016.04.14)

- Support for automatic reading in of arbitrary files.

## 0.14.1 (2016.04.14)

- Refactor `workplan.py`.

## 0.14.0 (2016.04.11)

- Adding change set support.

## 0.13.3 (2016.04.11)

- Moving dependency resolver code from `workplan.py` to `stack.py`.

## 0.13.2 (2016.04.7)

- Refactoring `stack.py`.

## 0.13.1 (2016.04.7)

- Improving troposphere template not found exception.

## 0.13.0 (2016.04.6)

- Adding `$ sceptre --version`.

## 0.12.1 (2016.04.6)

- Hiding internal class names.

## 0.12.0 (2016.04.6)

- Adding support for reading in environment variables for use as CloudFormation
  parameters.

## 0.11.0 (2016.03.31)

- Adding `continue-update-rollback` command.

## 0.10.2 (2016.03.31)

- Refactoring ConfigReader.

## 0.10.1 (2016.03.31)

- Updating documentation.

## 0.10.0 (2016.03.31)

- Adding Troposphere data injection support.

## 0.9.1 (2016.03.21)

- Minor refactor.

## 0.9.0 (2016.03.21)

- Adding --debug option.

## 0.8.2 (2016.03.21)

- Adding date time to printed out stack events.

## 0.8.1 (2016.03.21)

- Fixing bug in generate-template.

## 0.8.0 (2016.03.21)

- Sceptre now prints out stack events as stacks are being launched or deleted.

## 0.7.1 (2016.03.18)

- Refactoring interactor commands.

## 0.7.0 (2016.03.17)

- Adding lock-stack and unlock-stack commands.

## 0.6.3 (2016.03.16)

- Adding improved error handling for when users enter incorrect stack names.

## 0.6.2 (2016.03.16)

- Adding improved error handling for when users enter incorrect environment
  paths.
- Refactoring config_reader

## 0.6.1 (2016.03.15)

- Updating documentation.

## 0.6.0 (2016.03.15)

- Adding support for user-defined config directory structure.

## 0.5.1 (2016.03.10)

- Sceptre waits after checking a stack's status. This update drops the wait time
  from 3s to 1s.

## 0.5.0 (2016.03.10)

- Adds sceptre validate-template <env> <stack_name> command.

## 0.4.0 (2016.03.10)

- Sceptre now creates, updates and launches stacks from a template it uploads to
  s3.

## 0.3.2 (2016.03.10)

- Fixing create_bucket for region us-east-1.

## 0.3.1 (2016.03.10)

- Sceptre removes trailing slash from template_bucket_name.

## 0.3.0 (2016.03.09)

- Sceptre now appends time since epoch to uploaded JSON template names.

## 0.2.0 (2016.03.09)

- Sceptre now appends region to supplied bucket name.

## 0.1.3 (2016.03.08)

- Adding support for subdirectories in the template_bucket_name param.

## 0.1.2 (2016.03.08)

- Updating Troposphere to version 1.5.0.

## 0.1.1 (2016.03.08)

- Updating tox to only support Python 2.6 versions > 2.6.9.

## 0.1.0 (2016-03-07)

- Changing how parameter chaining is stated in yaml files.

## 0.0.1 (2015-12-13)

- First release.
