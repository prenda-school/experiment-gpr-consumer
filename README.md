# experiment-gpr-consumer
Part of "Experimenting with GitHub Packages".

This is a repository consuming (installing) packages from the GitHub Packages npm registry, specifically our organization's packages, and the regular npm registry.

### Guide (specific to our organization)
1. Generate a pesonal access token from your personal "Settings -> Developer Settings -> Personal Access Tokens" page. The token should be generated with at least the `repo` and `read:packages` scopes. 
2. Authenticate by logging in to npm, use the `npm login` command, replacing _USERNAME_ with your GitHub username, _TOKEN_ with your personal access token, and _PUBLIC-EMAIL-ADDRESS_ with your email address.
```bash
$ npm login --scope=@prenda-school --registry=https://npm.pkg.github.com

> Username: USERNAME
> Password: TOKEN
> Email: PUBLIC-EMAIL-ADDRESS
```
3. In the same directory as your `package.json` file, create or edit an `.npmrc` file to include a line specifying GitHub Packages URL and the account owner.
```.npmrc
@prenda-school:registry=https://npm.pkg.github.com
```
4. Install the package.
```bash
$ npm install @prenda-school/experiment-gpr-single
```

#### Sources
 - Reference for installing: https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-npm-registry#installing-a-package
   - When authenticating in step 1, there are two options ([see here](https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-npm-registry#authenticating-to-github-packages)):
     - **prerequisite:** `TOKEN` is generated from your personal Settings/Developer Settings/Personal Access Tokens page. The token should be generated with at least the `repo` and `read:packages` scopes.
     - Configure in `.npmrc` by adding `//npm.pkg.github.com/:_authToken=TOKEN`
       - Disadvantage: possibly commit your access token! or ignore file and have more opaque setup
       - ~~Advantage: per-project configuration~~ ; not actually an advantage because scopes can't be duplicated
     - Or, login to npm for the GitHub Packages registry and necessary scope: `npm login --scope=@prenda-school --registry=https://npm.pkg.github.com`
       - Doesn't have above problem

#### See more
- [repository publishing a single package](https://github.com/prenda-school/experiment-gpr-single)
- [repository publishing multiple packages](https://github.com/prenda-school/experiment-gpr-multiple)
