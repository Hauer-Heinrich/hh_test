# Github Actions for TYPO3 Extensions

## How to automatically create/publish a new Release on TYPO3 TER
1. Copy .github folder to your own Repository / Project (just once)
2. Get your TYPO3 API Token at [extensions.typo3.org](https://extensions.typo3.org/) (register if not already)
3. Navigate to "My access tokens" and create a TYPO3 "Access Token" (set expiration date to a value of your choice)
4. Add the TYPO3 Access Token to your Github, call it "TYPO3_API_TOKEN" (at settings->Secrets and variables or use the URL https://github.com/USERNAME/REPOSITORYNAME/settings/secrets/actions)
5. Edit composer.json and ext_emconf.php and change the Version Number
6. Then execute (replace the version): 
    ```
    VERSION="X.X.X" && git add --all && git commit -m "New Version $VERSION" && git tag "$VERSION" && git push && git push --tags
    ```
7. Check if the Github Action has been successfully executed, go to your Repository and click on the "Actions" Tab (or the URL similar to https://github.com/USERNAME/REPOSITORYNAME/actions)

The next time you want to create a release use the steps 5., 6. and 7. 

## Useful resources: 
See docs for glob pattern: 

- https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions#filter-pattern-cheat-sheet
- https://github.com/actions/runner/issues/1699
