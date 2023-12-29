name: 📜 Repository licenses
category: github
description: |
  This plugin display repository license informations like permissions, limitations and conditions along with additional stats about dependencies.
notes: |
  > ⚠️ This is **NOT** legal advice, use at your own risk

  > 💣 This plugin **SHOULD NOT** be enabled on web instances, since it allows raw command injection.
  > This could result in compromised server!
examples:
  +permissions, limitations and conditions: https://github.com/lowlighter/metrics/blob/examples/metrics.plugin.licenses.svg
  +licenses overview: https://github.com/lowlighter/metrics/blob/examples/metrics.plugin.licenses.ratio.svg
index: 6
supports:
  - repository
scopes:
  - public_access
inputs:

  plugin_licenses:
    description: |
      Enable licenses plugin
    type: boolean
    default: no
    extras:
      - metrics.cpu.overuse
      - metrics.run.tempdir
      - metrics.run.git
      - metrics.run.licensed
      - metrics.run.user.cmd

  plugin_licenses_setup:
    description: |
      Setup command

      > ℹ️ Depending on the project, this may not be required.
      > The example command is intended for NodeJs projects that use `npm` to install their dependencies.
    type: string
    default: ""
    example: "bash -c '[[ -f package.json ]] && npm ci || true'"

  plugin_licenses_ratio:
    description: |
      Used licenses ratio
    type: boolean
    default: no

  plugin_licenses_legal:
    description: |
      Permissions, limitations and conditions about used licenses
    type: boolean
    default: yes
