### OhMyDeploy 🚀

A reusable GitHub Actions workflow for deploying static sites to Cloudflare Pages (preview and production) with clear build logs and summaries.

## Features

- **Preview & Production**: Ship previews by default, promote to production on demand
- **Build Summary**: Rich step summary with build logs and metadata
- **Safe Concurrency**: Cancel in-progress runs per ref
- **Simple Inputs**: Minimal config to get started

## Usage

```yaml
name: Deploy website

on:
  push:
  workflow_dispatch:
    inputs:
      deploy_production:
        description: Deploy to production?
        required: false
        default: false
        type: boolean

jobs:
  deploy:
    uses: OhMyHost-se/OhMyDeploy/.github/workflows/deploy.yml@v1
    with:
      project_name: my-pages-project
      deploy_production: ${{ inputs.deploy_production }}
      website_url: https://example.com
    secrets:
      CLOUDFLARE_API_TOKEN: ${{ secrets.CLOUDFLARE_API_TOKEN }}
      CLOUDFLARE_ACCOUNT_ID: ${{ secrets.CLOUDFLARE_ACCOUNT_ID }}
```

## License

MIT License — see [LICENSE](LICENSE).

---

Built with ❤️ by [OhMyHost.se](https://ohmyhost.se)

