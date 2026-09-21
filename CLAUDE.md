# Mandatory project conventions

These conventions are mandatory for this repository.

## Project language

English is the standard language for the entire project.

All repository artifacts must be written in English, including:

* source code and identifiers;
* documentation;
* directory names;
* file names;
* configuration files;
* infrastructure code;
* scripts;
* tests and test descriptions;
* commit messages;
* pull request titles and descriptions;
* issue templates;
* logs and user-facing messages produced by project-owned code;
* dashboards, alert names and runbooks.

Communication with the project owner must remain in Brazilian Portuguese.

Explanations, questions, plans, summaries and approval requests addressed to the project owner must be written in Portuguese. Repository content and Git history must be written in English.

Existing Portuguese repository content must be translated into English before it becomes part of the implementation baseline.

The approved architecture document must not be translated or rewritten silently. Its English version must:

1. preserve every approved decision, constraint, scope item and acceptance criterion;
2. introduce no architectural change;
3. retain traceability to version 0.1;
4. be reviewed as a translation-only change;
5. be approved by the project owner before replacing the Portuguese version as the authoritative document.

If a translation requires changing meaning, terminology or architecture, stop and request approval.

## File and directory naming

Use lowercase kebab-case for all project-owned file and directory names.

Examples:

* `cost-estimation.md`
* `platform-observability/`
* `validate-terraform.sh`
* `tenant-template.yaml`
* `architecture-decisions.md`

Do not use:

* spaces;
* underscores;
* PascalCase;
* camelCase;
* names written in Portuguese.

Do not rename ecosystem-standard or tool-required files merely to enforce kebab-case.

Approved exceptions include:

* `README.md`
* `CLAUDE.md`
* `CODEOWNERS`
* `LICENSE`
* `NOTICE`
* `Dockerfile`
* `Makefile`
* `CHANGELOG.md`
* `SECURITY.md`
* `CONTRIBUTING.md`
* `main.tf`
* `variables.tf`
* `outputs.tf`
* `versions.tf`
* `providers.tf`
* `.gitignore`
* `.gitattributes`
* `.editorconfig`
* tool-generated lock files;
* filenames required by GitHub, Terraform, Helm, Kubernetes or another selected tool.

When a tool establishes a canonical filename, follow the tool convention and document the exception only when it is not self-evident.

## Conventional Commits

All commits must follow the Conventional Commits specification.

Use the following structure:

`<type>(<optional-scope>): <description>`

Approved primary types:

* `feat`
* `fix`
* `docs`
* `refactor`
* `test`
* `build`
* `ci`
* `chore`
* `perf`
* `revert`

Requirements:

* write commit messages in English;
* use lowercase for the type and scope;
* use the imperative mood;
* keep the description concise;
* do not end the description with a period;
* use a scope when it improves traceability;
* use `!` and a `BREAKING CHANGE:` footer only for actual breaking changes.

Examples:

* `docs(architecture): add approved platform baseline`
* `chore(repository): add initial governance files`
* `ci(validation): add markdown lint workflow`
* `feat(terraform): add ephemeral state backend module`
* `test(policy): validate required ownership labels`

## Staging and commit policy

Never use broad staging commands.

The following commands are prohibited:

* `git add .`
* `git add -A`
* `git add --all`
* wildcard-based staging;
* directory-wide staging.

Files must be reviewed, staged and committed individually.

The default workflow is:

```shell
git diff -- <file>
git add <file>
git diff --cached -- <file>
git commit -m "<conventional-commit-message>"
```

Only one explicitly identified file may be staged for each commit.

Before every commit:

1. inspect the file diff;
2. stage only that file;
3. inspect the staged diff;
4. verify that no unrelated file is staged;
5. create a Conventional Commit in English.

If a generated operation modifies multiple files, process each file individually. Do not group them into a single commit without explicit authorization from the project owner.

Do not commit or push unless the project owner has explicitly authorized the action.

## Commit attribution

Do not add AI attribution to commits.

Commit messages must not contain:

* `Co-Authored-By: Claude`
* `Co-Authored-By: Claude Code`
* similar AI attribution;
* promotional or tool-generated signatures.

Do not use `--author` to impersonate another identity.

Use only the Git identity already configured by the project owner.

## Clean code and comments

Generate clean, self-explanatory code and configuration.

Do not add explanatory comments that merely restate what the code already expresses.

Avoid:

* tutorial-style comments;
* line-by-line explanations;
* decorative separators;
* comments describing obvious assignments;
* comments addressed to the project owner;
* comments mentioning AI generation;
* commented-out code;
* TODO comments without an approved backlog reference;
* verbose boilerplate that adds no operational value.

Prefer:

* descriptive names;
* small modules;
* clear interfaces;
* explicit variables;
* predictable directory structures;
* documentation in the appropriate Markdown file.

Comments are allowed only when they are technically necessary, including:

* required directives for linters, compilers or security scanners;
* required licensing headers;
* tool-required annotations;
* explanations of non-obvious constraints that cannot be expressed clearly in code;
* warnings that prevent a security, cost or lifecycle failure;
* references to an approved workaround or tracked issue.

When such a comment is necessary, keep it concise, factual and written in English.

Documentation files are not subject to the no-explanatory-comments rule. They must contain the prose required to explain architecture, operation, onboarding and troubleshooting.

## Enforcement

These conventions must be enforced where practical through automated checks, including:

* Conventional Commit validation;
* filename and directory-name validation;
* language review for repository artifacts;
* Markdown linting;
* secret detection;
* formatting and linting for source code and infrastructure;
* staged-file inspection before commits.

Do not introduce a validation tool before checking its maintenance status, official documentation, cost and compatibility with the project.

No automated enforcement tooling is installed in this repository yet. This section documents the target state; each check must be evaluated and adopted as a separate, explicit decision before it is wired into CI or pre-commit hooks.

If an external chart, module or generated artifact violates these conventions, do not modify vendor content solely for stylistic consistency. Apply the conventions only to project-owned files and document unavoidable exceptions.
