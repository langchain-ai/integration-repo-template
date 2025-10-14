# 🦜️🔗 LangChain {partner}

This repository contains 1 package with {partner} integrations with LangChain:

- [langchain-{package_lower}](https://pypi.org/project/langchain-{package_lower}/)

## Initial Repo Checklist (Remove this section after completing)

Welcome to the LangChain Partner Integration Repository! This checklist will help you get started with your new repository.

After creating your repo from the integration-repo-template, we'll go through how to
set up your new repository in Github.

This setup assumes that the partner package is already split. For those instructions,
see [these docs](https://docs.langchain.com/oss/python/contributing/integrations-langchain).

> [!NOTE]
> Integration packages can be managed in your own Github organization.

Code (auto ecli)

- [ ] Fill out the readme above (for folks that follow pypi link)
- [ ] Copy package into /libs folder
- [ ] Update `"Source Code"` and `repository` under `[project.urls]` in /libs/*/pyproject.toml

Workflow code (auto ecli)

- [ ] Populate .github/workflows/_release.yml with `on.workflow_dispatch.inputs.working-directory.default`
- [ ] Configure `LIB_DIRS` in .github/scripts/check_diff.py

Workflow code (manual)

- [ ] Add secrets as env vars in .github/workflows/_release.yml

Monorepo workflow code (manual)

- [ ] Pull in new code location, remove old in .github/workflows/api_doc_build.yml

In github (manual)

- [ ] Add any required integration testing secrets in Github
- [ ] Add any required partner collaborators in Github
- [ ] "Allow auto-merge" in General Settings (recommended)
- [ ] Only "Allow squash merging" in General Settings (recommended)
- [ ] Set up ruleset matching CI build (recommended)
    - name: ci build
    - enforcement: active
    - bypass: write
    - target: default branch
    - rules: restrict deletions, require status checks ("CI Success"), block force pushes
- [ ] Set up ruleset (recommended)
    - name: require prs
    - enforcement: active
    - bypass: none
    - target: default branch
    - rules: restrict deletions, require a pull request before merging (0 approvals, no boxes), block force pushes

Pypi (manual)

- [ ] Add new repo to test-pypi and pypi trusted publishing

> [!NOTE]
> Tag [@ccurme](https://github.com/ccurme) if you have questions on any step.
