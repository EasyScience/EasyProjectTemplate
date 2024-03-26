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
git remote add origin https://github.com:EasyScience/NewEasyProject.git
```
