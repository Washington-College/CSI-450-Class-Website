# Optional GitHub Actions Deployment

By default, this template is set up for manual deployment:
1. Run `quarto render` locally
2. Commit the `docs/` folder
3. Enable GitHub Pages from the `docs/` folder

However, if you prefer **automated deployment**, you can use the included GitHub Actions workflow.

## Enabling GitHub Actions Deployment

### Step 1: Enable the Workflow

The workflow file already exists at `.github/workflows/publish.yml`. It will automatically run when you push to the `main` branch.

### Step 2: Configure GitHub Pages for Actions

1. Go to your repository on GitHub
2. Click **Settings** → **Pages**
3. Under **Build and deployment**:
   - **Source**: Select "GitHub Actions" (instead of "Deploy from a branch")

### Step 3: Push Your Changes

```bash
git add .
git commit -m "Enable GitHub Actions deployment"
git push origin main
```

The workflow will automatically:
- Install Quarto
- Render your website
- Deploy to GitHub Pages

## Benefits of GitHub Actions Deployment

✅ **Automatic**: No need to run `quarto render` locally  
✅ **Clean**: No need to commit the `docs/` folder  
✅ **Consistent**: Same build environment every time  
✅ **Faster**: Push changes and forget about it

## Switching Back to Manual Deployment

If you prefer manual deployment:

1. Go to **Settings** → **Pages**
2. Change **Source** back to "Deploy from a branch"
3. Select branch: `main`, folder: `/docs`

## Troubleshooting

### Workflow fails with permission error

Make sure GitHub Actions has the correct permissions:
- Go to **Settings** → **Actions** → **General**
- Under "Workflow permissions", select "Read and write permissions"
- Click **Save**

### Changes aren't appearing on the site

- Check the **Actions** tab to see if the workflow completed successfully
- Allow 2-5 minutes for changes to propagate
- Clear your browser cache

## For Instructors

If you want all students to use GitHub Actions:

1. Delete these lines from `.gitignore`:
   ```
   /docs/
   ```
   
2. Update the student guide to reference GitHub Actions instead of manual rendering

3. In the assignment instructions, tell students to enable GitHub Actions in their Pages settings
