# Branch Migration Guide: Master to Main

## Summary

This document outlines the changes made to prepare the repository for migrating from `master` to `main` as the default branch, and the remaining steps that require repository administrator privileges.

## ✅ Completed Changes

### 1. Documentation Updates
- **README.md**: Updated all branch references from `master` to `main`
  - License badge URL
  - All screenshot image URLs (5 total)
  - Repository references changed from upstream to this fork
- **.coderabbit.yaml**: Updated ignored branch from `l10n_master` to `l10n_main`

### 2. URL Validation
All updated URLs have been tested and return HTTP 200 status codes:
- https://github.com/azuravian/playnite-successstory-plugin-fork/blob/main/LICENSE
- https://github.com/azuravian/playnite-successstory-plugin-fork/blob/main/forum/main_01.jpg
- https://github.com/azuravian/playnite-successstory-plugin-fork/blob/main/forum/main_02.jpg
- https://github.com/azuravian/playnite-successstory-plugin-fork/blob/main/forum/control_01.jpg
- https://github.com/azuravian/playnite-successstory-plugin-fork/blob/main/forum/settings_01.jpg

### 3. Repository State
- Both `main` and `master` branches exist with identical content
- Git submodules properly initialized
- No remaining `master` references in configuration or documentation files

## 🔧 Required Administrator Actions

### Step 1: Change Default Branch
1. Go to repository **Settings** → **General**
2. Scroll to **Default branch** section
3. Change from `master` to `main`
4. Click **Update** and confirm the change

### Step 2: Delete Master Branch
1. Go to repository **Settings** → **Branches** 
2. Find the `master` branch in the branch list
3. Click the **Delete** button for the master branch
4. Confirm deletion

### Step 3: Update Branch Protection Rules (if applicable)
- Review any branch protection rules
- Update rules that reference `master` to reference `main` instead

### Step 4: Update CI/CD References (if applicable)
- Check GitHub Actions workflows in `.github/workflows/`
- Update any hardcoded branch references from `master` to `main`

## 📋 Post-Migration Checklist

After completing the administrator actions:
- [ ] Verify default branch is set to `main`
- [ ] Verify `master` branch is deleted
- [ ] Test that README images display correctly
- [ ] Verify any automated workflows still function
- [ ] Update any external references or bookmarks to the repository

## 🔍 Impact Assessment

**Breaking Changes**: None expected
- All URLs now point to working resources in the `main` branch
- Documentation is self-consistent within this fork
- No code functionality is affected

**Benefits**:
- Aligns with modern Git conventions
- Removes dependency on the `master` branch name
- Ensures fork documentation points to fork resources

## 🤝 Support

If you encounter any issues during the migration:
1. Verify all URLs in README.md are accessible
2. Check that the `main` branch contains all expected files
3. Ensure no other repository configurations reference the old branch name

The code changes in this PR prepare the repository for a smooth transition and can be safely merged before performing the administrative branch changes.