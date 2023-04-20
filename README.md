# AISG's Cookiecutter Template for End-to-end ML Projects (GCP)

## Table of Contents

- [AISG's Cookiecutter Template for End-to-end ML Projects (GCP)](#aisgs-cookiecutter-template-for-end-to-end-ml-projects-gcp)
  - [Table of Contents](#table-of-contents)
  - [Preface](#preface)
  - [Usage](#usage)
    - [Input Parameters](#input-parameters)
    - [Version Control](#version-control)
    - [Updating Template Repository](#updating-template-repository)

## Preface

This repository contains the
[`cookiecutter`](https://cookiecutter.readthedocs.io/en/stable/)
template for generating a repository that provides boilerplates touching
on the differing components of an end-to-end ML project. This template
is dedicated for the GCP environment.

## Usage

To use the template and create a repository, you would need to
[install the `cruft` CLI](https://cruft.github.io/cruft/)
, say within a virtual environment and pass the URL of this template as
an argument, like such:

```bash
$ pip install cruft
$ cruft create https://github.com/aisingapore/ml-project-cookiecutter-gcp
```

__Note:__ `cruft` can quickly validate whether or not a project is using
the latest version of a template using `cruft check`.

You will then be prompted to provide inputs.These inputs will be used to
populate different parts of the repository to be generated by
`cookiecutter`.

### Input Parameters

|         Parameter        | Detail                                                                                                                                         | Default                                                                     | Choices                                      |
|:------------------------:|------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------|----------------------------------------------|
|      `project_name`      | Name of project that will be the header for the `README.md`. Recommended for input to start with alphabet characters. Use whitespace instead of underscores or hyphens. | NIL                                                | NIL                                          |
|       `description`      | A short description of the project that will be populated in `README.md`.                                                                      | A short description of the project.                                         | NIL                                          |
|        `repo_name`       | Name of the repository folder. Recommended for input to start with alphabet characters. No whitespaces are allowed.                            | `project_name` where whitespaces and underscores are replaced with hyphens. | NIL                                          |
|    `src_package_name`    | Name of the source code's package under `src`. Recommended for input to start with alphabet characters. No whitespaces or hyphens are allowed. | `repo_name` where hyphens are replaced with underscores.                    | NIL                                          |
| `src_package_name_short` | The alias for the source code's package.                                                                                                       | `src_package_name`                                                          | NIL                                          |
|     `gcp_project_id`     | ID of your GCP project.                                                                                                                        | NIL                                                                         | NIL                                          |
|   `gcr_personal_subdir`  | Whether you are making use of personal subdirectories for GCR repositories.                                                                    | NIL                                                                         | 1 - Yes, 2 - No                              |
|       `author_name`      | Your alias or project team's name. Underscore delimited if you're using personal GCR subdirectories (__case sensitive__).                      | NIL                                                                         | NIL                                          |
|   `open_source_license`  | Open source license to be populated within repository. When in doubt, select [3].                                                              | NIL                                                                         | 1 - MIT, 2 - BSD-3-Clause, 3 - No license file |

__Note:__ If invalid inputs are provided, `cruft`
(with `cookiecutter` in the backend) will exit and
the repository will not be generated.

### Version Control

Following the creation of your repository,
initialise it with Git, push it to a
remote, and follow its
`README.md` document for a full guide on its usage.

### Updating Template Repository

Over time, this `cookiecutter` template will be updated. The first time
you create the template repository using `cruft`, it a `.cruft.json`
file is created as well. This JSON configuration file details
the latest commit hash of this `cookiecutter` template it was derived
from. When you execute `cruft check`, if the commit hash
in `.cruft.json` differs from the latest commit hash that exist
on the remote of this `cookiecutter` template, an error will be
returned.

```bash
$ cruft check
FAILURE: Project's cruft is out of date! Run `cruft update` to clean this mess up.
```

To compare the difference between your template repository
and the one that exists on the remote, you can run `cruft diff`
and see what changes would be applied should you execute
`cruft update`.

If you would like to exclude certain files or directories from
being affected by `cruft` updates, you can look into using the
`--skip` flag or configuration.

Reference(s):

- [`cruft` Docs - Updating A Project](https://cruft.github.io/cruft/#updating-a-project)