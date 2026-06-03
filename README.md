<div align="center">

<img src="https://capsule-render.vercel.app/api?type=transparent&height=80&text=%F0%9F%91%8B%20Hi,%20I%27m%20saysaa!&fontSize=38&fontColor=ffffff&fontAlignY=50" />

<img src="https://img.shields.io/badge/Location-Lyon,%20France%20%F0%9F%87%AB%F0%9F%87%B7-blue?style=flat-square" alt="Lyon, France">

<br><br>

<img src="https://capsule-render.vercel.app/api?type=transparent&height=60&text=%F0%9F%93%8A%20GitHub%20Stats&fontSize=30&fontColor=ffffff&fontAlignY=50" />

<br>

<img width="400" src="https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=saysaa&theme=github_dark" />
<img width="400" src="https://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=saysaa&theme=github_dark" />

<br><br>

<img width="400" src="https://github-profile-summary-cards.vercel.app/api/cards/productive-time?username=saysaa&theme=github_dark&utcOffset=2" />
<img width="400" src="https://github-profile-summary-cards.vercel.app/api/cards/stats?username=saysaa&theme=github_dark" />

<br><br>

<img src="https://capsule-render.vercel.app/api?type=transparent&height=60&text=%F0%9F%93%AB%20Contact&fontSize=30&fontColor=ffffff&fontAlignY=50" />

<br>

<img src="https://img.shields.io/badge/Discord-saysaa__-5865F2?style=for-the-badge&logo=discord&logoColor=white" />

</div>


# Visit https://github.com/lowlighter/metrics#-documentation for full reference
name: Metrics
on:
  # Schedule updates (each hour)
  schedule: [{cron: "0 * * * *"}]
  # Lines below let you run workflow manually and on each commit
  workflow_dispatch:
  push: {branches: ["master", "main"]}
jobs:
  github-metrics:
    runs-on: ubuntu-latest
    permissions:
      contents: write
    steps:
      - uses: lowlighter/metrics@latest
        with:
          # Your GitHub token
          # The following scopes are required:
          #  - public_access (default scope)
          #  - public_repo
          #  - read:project
          # The following additional scopes may be required:
          #  - read:org      (for organization related metrics)
          #  - read:user     (for user related data)
          #  - read:packages (for some packages related data)
          #  - repo          (optional, if you want to include private repositories)
          token: ${{ secrets.METRICS_TOKEN }}

          # Options
          user: saysaa
          template: terminal
          base: header, activity, community, repositories, metadata
          config_timezone: Europe/Paris
          plugin_introduction: yes
          plugin_introduction_title: yes
          plugin_isocalendar: yes
          plugin_isocalendar_duration: full-year
          plugin_projects: yes
          plugin_projects_descriptions: yes
          plugin_projects_limit: 4
          plugin_projects_repositories: https://github.com/saysaa/ReSharp3DS, https://github.com/saysaa/CIATools, https://github.com/saysaa/CTRTux,
