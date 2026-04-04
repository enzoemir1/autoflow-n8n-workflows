# Contributing to AutoFlow n8n Workflows

Thanks for your interest in contributing! Whether it's a bug fix, new workflow, or documentation improvement — all contributions are welcome.

## How to Contribute

### Report a Bug
1. Open an [Issue](https://github.com/enzoemir1/autoflow-n8n-workflows/issues) with the **Bug Report** template
2. Include your n8n version, the workflow name, and steps to reproduce

### Suggest a Feature
1. Open an [Issue](https://github.com/enzoemir1/autoflow-n8n-workflows/issues) with the **Feature Request** template
2. Describe the use case and expected behavior

### Submit a Workflow
1. Fork this repository
2. Create a new branch: `git checkout -b add-my-workflow`
3. Add your workflow JSON to the `workflows/` folder
4. Add documentation to the `docs/` folder (follow existing format)
5. Update `README.md` to include your workflow in the table
6. Submit a Pull Request

### Improve Documentation
- Fix typos, clarify setup steps, add examples
- PRs for documentation improvements are always appreciated

## Workflow Guidelines

When submitting a new workflow:

- **Use gpt-4o-mini** as the default model (cost-effective)
- **Include a webhook trigger** so users can test immediately
- **Log outputs to Google Sheets** for easy verification
- **Add clear comments** in n8n sticky notes within the workflow
- **Test the workflow** on a fresh n8n instance before submitting
- **Keep costs low** — aim for under $0.01 per execution

## Code of Conduct

Be respectful, constructive, and helpful. We're all here to build useful automations.

## Questions?

Open an issue or reach out on [Twitter/X](https://x.com/automatiabcn).
