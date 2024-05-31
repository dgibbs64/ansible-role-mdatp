# mdatp

An [Ansible](https://www.ansible.com) role that installs and configures <a href="https://learn.microsoft.com/en-us/defender-endpoint/microsoft-defender-endpoint-linux">Microsoft Defender for Endpoint on Linux</a>.

<p align="center">
<a href="https://app.codacy.com/gh/dgibbs64/ansible-role-mdatp"><img src="https://img.shields.io/codacy/grade/1a892d499efd4dabb73beffa8d64ed01?logo=codacy&style=flat-square" alt="Codacy grade"></a>
<a href="https://github.com/dgibbs64/ansible-role-mdatp/actions/workflows/molecule.yml"><img alt="GitHub Workflow Status" src="https://img.shields.io/github/actions/workflow/status/dgibbs64/ansible-role-mdatp/molecule.yml?label=molecule&logo=ansible&style=flat-square"></a>
<a href="https://galaxy.ansible.com/dgibbs64/mdatp"><img alt="GitHub tag (latest by date)" src="https://img.shields.io/github/v/tag/dgibbs64/ansible-role-mdatp?color=EE0000&label=release&logo=ansible&style=flat-square"></a>
<a href="https://github.com/dgibbs64/ansible-role-mdatp/blob/main/LICENSE.md"><img src="https://img.shields.io/github/license/gameservermanagers/docker-steamcmd?style=flat-square" alt="MIT License"></a>
</p>

## About

<a href="https://learn.microsoft.com/en-us/defender-endpoint/microsoft-defender-endpoint-linux">Microsoft Defender for Endpoint on Linux</a> is a unified endpoint security platform that helps stop breaches. It is designed to help enterprise networks prevent, detect, investigate, and respond to advanced threats.

## Requirements

Requires a <a href="https://learn.microsoft.com/en-us/defender-endpoint/microsoft-defender-endpoint">Microsoft Defender for Endpoint</a> License. You will also need to download `WindowsDefenderATPOnboardingPackage.zip` from the <a href="https://securitycenter.windows.com">Microsoft Defender Security Center</a>. Instuctions found <a href="https://learn.microsoft.com/en-us/defender-endpoint/linux-install-manually#download-the-onboarding-package">here</a>.

### Supported Distros

- AlmaLinux >= 8
- AmazonLinux 2023
- CentOS >= 7
- Debian >= 9
- Fedora >= 33
- openSUSE >= 15.4
- OracleLinux >= 8
- Redhat Enterprise Linux >= 8
- Rocky Linux >= 8
- Ubuntu >= 20.04

## Role Variables

```yaml
# enable apt-mark hold
mdatp_apt_package_version_hold: false
# Test connectivity to Microsoft
mdatp_connectivity_test: false
# Test health of MDATP
mdatp_health_test: true
# Microsoft repository channel insiders-fast|insiders-slow|prod
mdatp_microsoft_repo_channel: "prod"
# MDATP Onboaring Package file location
mdatp_onboarding_package_location: "WindowsDefenderATPOnboardingPackage.zip"
# MDATP state present|absents
mdatp_state: "present"
# MDATP YUM package version lock mdatp-101.24032.0007-1
mdatp_yum_package_version:
# Prevent the microsoft repository from being installed
mdatp_microsoft_repo_install_disable: false
```

## Dependencies

```yaml
community.general
```

## Example Playbook

```yaml
---
- name: mdatp
  hosts: all
  roles:
    - dgibbs64.mdatp
```

## License

MIT

## Author Information

- [Daniel Gibbs](https://danielgibbs.co.uk)
