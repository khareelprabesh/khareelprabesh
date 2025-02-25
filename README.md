name: GitHub Metrics
on:
  schedule: [{cron: "0 0 * * *"}] # Updates daily
  workflow_dispatch:

jobs:
  metrics:
    runs-on: ubuntu-latest
    steps:
      - uses: lowlighter/metrics@latest
        with:
          filename: github-metrics.svg
          token: ${{ secrets.METRICS_TOKEN }}
          base: header, activity, community, repositories, metadata
          plugin_languages: yes
