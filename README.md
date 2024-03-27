# Copier template for EasyScience projects

See [copier](https://copier.readthedocs.io/en/stable/) for details.
Usage example:

Create an empty project named `NewEasyProject` on GitHub

```sh
copier copy gh:/EasyScience/EasyProjectTemplate NewEasyProject # requires python>=3.9
cd NewEasyProject
git init .
git add * .copier-answers.yml .github .gitignore
git commit -m "Setup from EasyProjectTemplate"
git remote add origin git@github.com:EasyScience/NewEasyProject.git
git push origin master
```

Alternatively, the add remote step can be invoked using https:
```sh
git remote add origin https://github.com/EasyScience/NewEasyProject.git
```
## Manual Configuration

Once the project is built from the template, there are manual settings to be configured per project/repository.

### Documentation Deployment

1. Select branch of deployed documentation.
   The documentation will be deployed from a branch via GitHub action.
   The branch of the documentation must be selected manually on GitHub.
   Go to `Settings > Pages` and set `source` as  `Deploy from a branch` and `Branch` as `gh-pages`.

2. Enable website link on repository page.
   Once the branch for the documentation is selected after step `1`, it can be shown in the repository page.
   Go to `repository page` > `About section` (in the right sidebar).
   Click the gear and check the "Use your GitHub Pages website" checkbox for "Website".

### Package Deployment

#### PyPI

1. Create a new project by [adding a trusted publisher](https://docs.pypi.org/trusted-publishers/creating-a-project-through-oidc/).
2. In the GitHub project settings, go to `Environments` and add a new environment `release`.
   Configure appropriate protection rules such as required reviewers and deploying only from protected branches.

### Branch Protection Rules
Go to `Settings > Branches` and in the `Branch protection rules` add rule for `main` branch to project it.
Under `Protect matching branches` setting, select
- [ ] `Require a pull request before merging`
- [ ] `Require approvals`
- [ ] `Require branches to be up to date before merging`
- [ ] `Require status checks to pass before merging`

      You can either use all checks, or select `required` checks only.
      The list of jobs you can select as `required` checks will be shown only after they are triggered at least once within a week.
