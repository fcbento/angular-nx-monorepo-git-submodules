# Angular NX monorepo and Git submodules

Minimal setup for using Nx monorepos for an Angular based project using git submodules. It basically enables to have multiple teams working in the same project but in different repositories, enhancing developer productivity. I followed this [tutorial](https://nx.dev/getting-started/tutorials/angular-monorepo-tutorial) to achieve the result and did a little research to understand about [git submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules). The main app holds the codebase for multiple projects, components, libraries or shared UIs related of the same system.

## Prerequisites

Requirements for running the app locally
- [Node](https://nodejs.org/)
- [Npm](https://www.npmjs.com/)


## How it was achieved

##### Create the workspace and add a remote git repository.
```npx create-nx-workspace@latest angular-nx-monorepo-git-submodules --preset=angular-monorepo --skipGit```

##### Go into the repository
```cd angular-nx-monorepo-git-submodules```

##### Remove the default created app so that we can create a new app and add a gitsubmodule to it. Maybe review this step?
```rm -rf apps/angular-nx-monorepo-git-submodules```

##### Git initialization (main repository)
```
git init
git add .
git commit -m "feat: create workspace"
git branch -M main
git remote add origin https://github.com/fcbento/angular-nx-monorepo-git-submodules.git
git push -u origin main
```

### Adding submodules

#### - Create a new git repository

```cd apps```

##### Add a git submodule
```git submodule add https://github.com/fcbento/angular-nx-project-example.git```

##### Create new Angular app
```npx nx g @nx/angular:app apps/angular-nx-project-example```

##### Serve
```npx nx serve app-example-one```

##### Get changes from monorepo
```git submodule foreach git pull```

### Git submodules

<img alt="example" width="800" src="gitsubmodule.png">

### Main application

<img alt="example" width="800" src="commit.png">

### TODO

- [ ] Create a monorepo for a shared library
- [ ] Improve this documentation
  
## Built With

This was created with the following tech stack.

## [Nx](https://nx.dev/)

[![My Skills](https://skillicons.dev/icons?i=angular,nodejs,typescript,vscode&perline=10)](https://skillicons.dev)


## Top contributors

<a href="https://github.com/fcbento/node-prisma-docker-postgresql-ci/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=fcbento/node-prisma-docker-postgresql-ci" alt="contrib.rocks image"/>
</a>

## Contact

[![linkedin](https://skillicons.dev/icons?i=linkedin)](https://linkedin.com/in/felipe-bento)
[![discord](https://skillicons.dev/icons?i=discord)](https://discordapp.com/users/413141379074490369)
[![gmail](https://skillicons.dev/icons?i=gmail)](mailto:felipe.16costa@gmail.com)