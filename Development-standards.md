> [!NOTE]
> Code standard will appear as the project goes, but none is set for now.

# VCS Workflow

## Issues

Each **Issue** must contain **sub-issues**.
Use the following naming format :

`type(scope): Description` 

## Branches
Use `kebab-case` for branch names.

==**Always**== create a new branch starting from `dev` before altering code.

> [!NOTE]
> Each branch must follow this format: `type/scope/details`
>	- `feat/scope/details`
>	- `fix/scope/details`
>	- `ref/scope/details`
>	- `hotfix/id/details`

**Example:**
```diff
+ feat/ui/create-login-menu // OK
- Feat/UI/CreateLoginMenu   // KO - The branch name is in PascalCase
- feat/ui/create_login_menu // KO - The branch name is in snake_case
```

## Commit

Use this form of [git karma](https://karma-runner.github.io/6.4/dev/git-commit-msg.html):
	- **Feature**: `feat(scope): description`
	- **Fix**: `fix(scope): description`
	- **Refactor**: `ref(scope): description`
	- **Fixing coding style**: `style(scope): description`

> [!IMPORTANT]
> Use a preterit action verb for the description 

## Merges

1. Create a new pull request

2. Link the issues to the newly created PR.

3. Write a quick summary of the features.

4. Write a precise description of the changes.

5. **If** There is breaking changes, notify it and precise which changes are breaking.

6. Add screenshots / Videos if possible.  

7. Follow the completion checklist. 

> [!NOTE]
> For `main` and `dev`, **PR** must be reviewed by at least 1 member

## Releases

To ensure consistency across our repositories and clear communication with stakeholders, the **Lumaely** project follows the **Semantic Versioning 2.0.0 (SemVer)** standard. Every release must follow a predictable sequence to signal the impact of changes to our users and automated CI/CD pipelines.

All versions of Lumaely are formatted as follows: 
`[ProjectName] [MAJOR].[MINOR].[PATCH]-[PRE-RELEASE].[IDENTIFIER]`
**Example:** `Lumaely 1.4.18-alpha.77`

### MAJOR (Breaking changes)

**format :** `1.x.x`
**Increment :** When you make incompatible API changes or structural shifts that require the other end to refactor their implementation.
> [!NOTE]
> When the Major version is incremented, Minor and Patch must be reset to `0`.

### MINOR (New feature)

**format :** `x.4.x`
**Increment :** When you add functionality in a backwards-compatible manner (e.g., adding a new endpoint or a new UI component).

> [!NOTE]
> When the Minor version is incremented, the Patch version must be reset to `0`.

### PATCH (Bug fixes)

**format :** `x.x.18`
**Increment :** When you push backwards-compatible bug fixes or performance optimizations. This is often referred to as a **Hotfix** when deployed outside the standard release cycle.

### Pre-release Identifiers

For the Lumaely project, we use suffixes to track progress through the development lifecycle. These are appended with a hyphen and followed by an incrementing number. 

| Identifier | Description | Example |
| :--- | :--- | :--- |
| **alpha** | Internal testing and active development. Unstable. | `Lumaely 1.4.18-alpha.77` |
| **beta** | Feature-complete, open for external/QA testing. | `Lumaely 1.4.18-beta.2` |
| **rc** | Release Candidate. Likely the final build for production. | `Lumaely 1.4.18-rc.1` |