This repo and the related `test-childrepo` exist to test pushing content from one repo to another
via a GitHub workflow.

I was ultimately able to pull this off with a workflow entirely within the parent repo,
with no CI setup required in the child repo.

The workflow in this repo makes use of a fine-grained PAT with read/write contents permission.
(According to GitHub, GitHub Apps are preferable over PATs for long-term infrastructure
in organization repos, but those seem to require quite a bit more setup and also a
server to run from.)

## Original Approach: Workflow Dispatch

I initially set this up using a small workflow in this repo to trigger a workflow even in the child repo.
The following pages helped with that:

- [Discussion RE triggering from another repository](https://github.com/orgs/community/discussions/26323)
- [Triggering a Workflow](https://docs.github.com/en/actions/using-workflows/triggering-a-workflow)
- [Create a workflow dispatch event](https://docs.github.com/en/rest/actions/workflows?apiVersion=2022-11-28#create-a-workflow-dispatch-event)
- [Events that Trigger Workflows: `push`](https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows#push)
- [Managing your Personal Access Tokens](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens)

The permissions involved for this approach seemed like they'd be a little more complex,
vs. only needing content read/write permission to accomplish the workflow all in this repo.
