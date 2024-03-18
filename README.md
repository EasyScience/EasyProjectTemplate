# Copier template for EasyScience projects

See [copier](https://copier.readthedocs.io/en/stable/) for details.
Usage example:

```sh
copier copy gh:/EasyScience/EasyProjectTemplate NewEasyProject # requires python>=3.9
cd NewEasyProject
git init .
git add * .copier-answers.yml .github .gitignore
git commit -m "Setup from EasyProjectTemplate"
git remote add origin git@github.com:EasyScience/NewEasyProject.git
```