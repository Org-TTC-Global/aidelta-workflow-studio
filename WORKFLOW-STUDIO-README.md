# Workflow Studio (Langflow Subtree Integration)

## Overview

This folder contains a subtree copy of our customised fork of Langflow.

Fork URL:\
https://github.com/Org-TTC-Global/aidelta-workflow-studio

This subtree setup allows:

- Editing Langflow directly inside the monorepo\
- Keeping developers synced automatically (no submodule init)\
- Pulling updates from our fork\
- Pushing changes back to our fork\
- Pulling updates from upstream Langflow through our fork

---

## Daily Development

All development happens inside:

    services/workflow-studio

Make UI changes, custom toolbar, branding, or backend integrations here.

Commit changes normally as part of the monorepo.

---

## Sync Commands

### Pull latest updates from our fork

    git subtree pull --prefix=services/workflow-studio workflow-studio-fork main --squash

### Push local subtree changes back into the fork

    git subtree push --prefix=services/workflow-studio workflow-studio-fork main

This keeps the fork updated with local customisations.

---

## Updating From Upstream Langflow

1.  Update your fork with upstream changes:

```
git fetch upstream
git merge upstream/main
git push origin main
```

2.  Pull the updated fork into the subtree:

```
git subtree pull --prefix=services/workflow-studio workflow-studio-fork main --squash
```

---

## Local Development Commands

Run Langflow locally:

    make run_cli

This launches the full Langflow UI and backend on your machine.

---

## Best Practices

- Do all work inside the subtree folder
- Do not edit the fork repo directly
- Keep custom UI changes isolated to reduce merge conflicts
- Push changes to the fork periodically for backup and versioning
- Treat this subtree as the working copy of Langflow inside the
  product

---

## Notes

This workflow ensures:

- Full control over custom UI
- Easy updating from upstream Langflow
- Seamless developer onboarding
- No dependency on submodules or init commands
