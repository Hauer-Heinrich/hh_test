# Github Actions for TYPO3 Extensions

## How to automatically create/publish a new Release on TYPO3 TER
1. Copy .github folder to your own Repository / Project
2. Edit composer.json and ext_emconf.php and change the Version Number
3. Then execute (replace the version): `VERSION="X.X.X" && git commit -am "New Version $VERSION" && git tag "$VERSION" && git push && git push --tags`
4. Check if the Github Action has been successfully executed, go to your Repository and click on the "Actions" Tab (usually something like https://github.com/username/repositoryname/actions)

## Useful resources: 
See docs for glob pattern: 

- https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions#filter-pattern-cheat-sheet
- https://github.com/actions/runner/issues/1699
