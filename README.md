# Push to Paragon GitHub Action

This GitHub Action allows you to push to Paragon using the Paragraph CLI.

## Usage

```yaml
name: Push to Paragon

on:
  push:

  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch: 

jobs:
  push_to_paragon:
    name: Push to Paragon
    runs-on: ubuntu-latest
      
    steps:
      - uses: actions/checkout@v4
      - id: push
        uses: useparagon/paragraph-push@v1
        with:
          paragonKey: ${{ secrets.PARAGON_CLI_KEY }}
          npmToken: ${{ secrets.NPM_TOKEN }}
          paragonZeusUrl: ${{ secrets.ZEUS_URL }}
          paragonDashboardUrl: ${{ secrets.DASHBOARD_URL }}
```

Make sure to replace ${{ secrets.PARAGON_CLI_KEY }}, ${{ secrets.NPM_TOKEN }}, ${{ secrets.ZEUS_URL }}, and ${{ secrets.DASHBOARD_URL }} with your actual secrets. Also, ensure to use the correct version of the action (useparagon/paragraph-push@d8ecfd354fb9637dc58013e1a1e24b4f22b8809b in this example).

## Inputs
- paragonKey
Required. Paragon CLI key for authentication.

- npmToken
Required. NPM token for package publishing.

- paragonZeusUrl
Required. URL for Paragon Zeus.

- paragonDashboardUrl
Required. URL for Paragon Dashboard.
