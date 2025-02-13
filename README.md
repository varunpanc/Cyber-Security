
# Cyber Security Assignment - GitHub Workflow & Deployment

## Project Overview  
This project demonstrates how to **commit changes, create pull requests, merge branches, and deploy a simple HTML page using GitHub Pages**. The project includes:  
- `index.html` – A simple redirect page.  
- `dashboard.html` or `linux.html` – The main page.  
- `styles.css` (if needed).  

---

## Git & GitHub Workflow  

### 1. Cloning the Repository  
To start working on the repository, clone it to your local machine:  
```sh
git clone https://github.com/your-username/your-repository.git
cd your-repository
```

### 2. Creating and Switching to a New Branch  
Instead of working directly on the `main` branch, create a new branch:  
```sh
git checkout -b feature-update
```
This helps in keeping changes organized.

### 3. Making Changes and Committing  
After modifying files (e.g., `dashboard.html`), add them to staging and commit:  
```sh
git add .
git commit -m "Updated dashboard with new styles"
```

### 4. Pushing Changes and Creating a Pull Request  
Push your changes to GitHub and create a **Pull Request (PR)**:  
```sh
git push origin feature-update
```
Then, go to the GitHub repository and create a **Pull Request (PR)**.  

### 5. Reviewing and Merging the Pull Request  
- The project maintainer reviews the **PR** for security and code quality.  
- If everything is fine, the **PR is merged** into the `main` branch.  
```sh
git checkout main
git merge feature-update
```

### 6. Deleting the Merged Branch (Cleanup)  
Once merged, delete the unnecessary branch to keep the repo clean:  
```sh
git branch -d feature-update
git push origin --delete feature-update
```

---

## Deploying on GitHub Pages  
### 1. Enable GitHub Pages  
1. Go to **Settings** → **Pages** in your repository.  
2. Under **Branch**, select `main` (or `gh-pages` if using a separate branch).  
3. Click **Save**.  

### 2. Ensure the Correct Entry Point  
- Rename `dashboard.html` to `index.html`, **OR**  
- Create an `index.html` that redirects to `dashboard.html`:
```html
<meta http-equiv="refresh" content="0; url=dashboard.html">
```

---

## Cyber Security Best Practices for GitHub  
1. **Never commit sensitive information** (e.g., passwords, API keys).  
2. **Use `.gitignore`** to prevent committing unnecessary files.  
3. **Review PRs before merging** to prevent malicious code injection.  
4. **Enable branch protection** for `main` to prevent direct edits.  
5. **Keep repository private** if it contains sensitive data.  

---

## Additional Recommendations  
1. **Automate security checks** using **GitHub Actions** or **Dependabot**.  
2. **Use signed commits** (`git commit -S`) for authentication.  
3. **Monitor logs and repo activity** to detect unauthorized access.  
4. **Use CodeQL Security Scans** for vulnerabilities in your code.
```
