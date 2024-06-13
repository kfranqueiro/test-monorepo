This repo and the related `test-childrepo` exist to test pushing content from one repo to another
via a GitHub workflow.

## Relevant Documentation

- [Discussion RE triggering from another repository](https://github.com/orgs/community/discussions/26323)
- [Triggering a Workflow](https://docs.github.com/en/actions/using-workflows/triggering-a-workflow)
- [Create a workflow dispatch event](https://docs.github.com/en/rest/actions/workflows?apiVersion=2022-11-28#create-a-workflow-dispatch-event)
- [Events that Trigger Workflows: `push`](https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows#push)
- [Managing your Personal Access Tokens](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens)

The parent repo makes use of a PAT with a few permissions;
I want to do more testing to narrow this down, but only content read/write was seemingly insufficient.
The child repo does not require a PAT whatsoever.
Ideally for long-term workflows under an organization it may be worth looking into a GitHub App
rather than using a PAT, but apps seem to require a server to run on.
