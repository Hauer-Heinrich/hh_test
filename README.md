# Github Actions for TYPO3 Extensions

## How to automate TYPO3 TER Upload / Deployment from Github

### Prerequisites (Access Token)
1. Get your TYPO3 API Token (if not already configured) at [extensions.typo3.org](https://extensions.typo3.org/)
2. Then navigate to "My access tokens" and create a TYPO3 "Access Token" (set expiration date to a value of your choice)<br>*(keep in mind that you need to refresh the token after expiration by repeating this step or by using the [TYPO3 Extension API](https://extensions.typo3.org/faq/rest-api))*
3. Add the TYPO3 Access Token to your Github, call it "TYPO3_API_TOKEN" (at settings->Secrets and variables or use the URL https://github.com/USERNAME/REPOSITORYNAME/settings/secrets/actions)

---

### Publish your TYPO3 Extension to Github+TYPO3 TER (automatically)
1. Go to your project/git folder and execute the following (if .github/workflows/main.yml does not exist): 
    ```
    mkdir -p .github/workflows && curl -Lo .github/workflows/main.yml https://raw.githubusercontent.com/Hauer-Heinrich/hh_test/main/.github/workflows/main.yml
    ```
2. Edit composer.json and ext_emconf.php and change the version number
3. Stage, commit, publish and tag all at once by executing the following (change X.X.X to your version): 
    ```
    VERSION="X.X.X" && git add --all && git commit -m "New Version $VERSION" && git tag "$VERSION" && git push && git push --tags
    ```
4. Check if the Github Action has been successfully executed, go to your Repository and click on the "Actions" Tab (or the URL similar to https://github.com/USERNAME/REPOSITORYNAME/actions)

---

### Useful resources: 
See docs for glob pattern: 

- https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions#filter-pattern-cheat-sheet
- https://github.com/actions/runner/issues/1699
