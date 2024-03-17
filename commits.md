## Conventions for git commits

I use these conventions for commits on personal repos.


### Commit Messages

> Inspiration: [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) & [Angular convention](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#-commit-message-guidelines)


#### Format:

```
<type>(scope): <description>
<BLANK LINE>
[optional body]
<BLANK LINE>
[optional footer(s)]
```


#### Types:

Types **MUST** be one of the following:
- **fix**: A bug fix.
- **feat**: Adds a new feature.
- **rm**: Removes a feature.
- **refactor**: A change to the structure of the code without affecting functionality.
- **revert**: Reverts a previous commit; see section Revert.
- **build**: Changes to the build system or external dependencies.
- **docs**: Changes to documentation only: `doc changes should be separate from code changes`.
- **ci/cd**: Changes to CI/CD configuration files and scripts.
- **merge**: A merge commit: `scope should be the name of the source branch`.


#### Scope:

The scope describes the area of the code base affected; it's **NOT OPTIONAL** and **MUST** be less than 30 characters.

In addition, it **MUST NOT** be a reference to an issue or PR.


#### Description:

A description **MUST** immediately follow the colon and space after the type/scope and **MUST** end with `;`.

In addition:

1. You **MUST NOT** capitalize the first letter.

2. Use the imperative, present tense: "change" not "changed" or "changes" (where reasonable).

3. Replace `and` with (`&` or `+`) also (where reasonable).


#### Body:

The body is optional; include whatever information you feel might be necessary.

Please separate paragraphs with newlines.

#### Footers:

Work in progress...
Each footer **MUST** in this format:
```
<TITLE>: <description>;
```

The title **MUST** be in all caps and immediately followed by a `:`.

The content is in free form, but **MUST** be immediately followed by a `;`.

For examples, see: `BREAKING CHANGE:` & `REVERT:`.

#### BREAKING CHANGE:

If a commit will introduce a breaking change, the type/scope **MUST** be followed by a `!` **AND** there **MUST** be a `BREAKING CHANGE: <description>;` footer describing what has been broken.


#### Revert:

If the commit reverts a previous commit, it **MUST** use the revert type and **MUST** have a `REVERT: <hash>;`, where hash is a `&` separated list of commit SHAs that are being reverted.

#### Init:

The initial commit message **MUST** be `init`.

### Examples:


```
rm(plugins.telescope)!: remove telescope keybindings previously moved to cmdline in e28fe18;

remove keybindings for creating and delete files, from telescope.

From now on use `e <path to file>` and `Delete <optional -r>` from the cmdline.

BREAKING CHANGE: telescope keybindings removed;
```

---

```
feat(Rect::contains): add method to check if self contains another rect;

adds a method to rect which allows you to check if one rect fits within the bounds of another.
```

---

```
fix(theme): fix theme selector not loading the correct saved theme;

I accidentally gave current_theme a default value, so it never loaded the save...
```

---

```
feat(autocomplete): add search & cmd path autocomplete;
```
