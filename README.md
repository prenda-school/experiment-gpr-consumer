# experiment-gpr-consumer
Part of "Experimenting with GitHub Packages".

This is a repository consuming (installing) packages from the GitHub Packages npm registry, specifically our organization's packages, and the regular npm registry.

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
