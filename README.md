# kicad-jekyll-report

## Commit Linting

This project uses **[Commitlint](https://github.com/conventional-changelog/commitlint)** to enforce consistent commit message formatting, following the [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) specification.

### Commit Message Format

Commit messages must follow this format:
<type>(<optional scope>): <subject>

- **type**: Describes the kind of change  
- **scope** (optional): Identifies the area of the codebase affected  
- **subject**: A short description of the change  

### Allowed Commit Types

The following commit types are allowed:

- `build` — Changes that affect the build system or external dependencies  
- `chore` — Routine tasks or maintenance  
- `ci` — Changes to CI configuration and scripts  
- `docs` — Documentation updates  
- `feat` — New features  
- `fix` — Bug fixes  
- `perf` — Performance improvements  
- `refactor` — Code changes that neither fix a bug nor add a feature  
- `revert` — Reverts a previous commit  
- `style` — Code style changes (formatting, white-space, etc.)  
- `test` — Adding or updating tests

### Usage  
Commitlint is configured in the `.git/hooks/commit-msg` hook to validate each user commit message automatically.
Node.js must be installed on the machine.  
When using `nvm` (Node Version Manager), activate and select the correct Node.js version by running:

```bash
nvm use
```