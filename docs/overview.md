---
sidebar_position: 100
slug: /
---

# tfaction

tfaction is a framework for Monorepo to build high level Terraform Workflows by GitHub Actions.
You don't have to run `terraform apply` in your laptop, and don't have to reinvent the wheel for Terraform Workflows anymore.

## Features

- Run `terraform plan` in pull requests, and run `terraform apply` by merging pull requests into the default branch
- [Dynamic build matrix for Monorepo](/tfaction/docs/feature/build-matrix)
  - CI is run on only changed working directories
- Notify the result of CI to pull requests with tfcmt, github-comment, and reviewdog
  - You don't have to check CI log
- [Run `terraform apply` safely using the plan file created by the merged pull request's `terraform plan`](/tfaction/docs/feature/plan-file)
- [Update related pull requests automatically when the remote state is updated](/tfaction/docs/feature/auto-update-related-prs)
  - Keep the result of CI including `terraform plan` up-to-date
- [Create a pull request automatically to follow up the apply failure](/tfaction/docs/feature/follow-up-pr)
- Support linters
  - terraform validate
  - [tfsec](https://github.com/aquasecurity/tfsec)
  - [trivy](https://github.com/aquasecurity/trivy)
  - [tflint](https://github.com/terraform-linters/tflint)
  - [conftest](https://www.conftest.dev/)
- [Support tfmigrate](/tfaction/docs/feature/tfmigrate)
- [Update dependencies by Renovate safely](/tfaction/docs/feature/renovate)
  - Prevent Renovate from applying unexpected changes, and enables to merge pull requests without changes safely
- [Workflows for Terraform Modules](/tfaction/docs/feature/module)
  - Scaffold, Test, Release Modules
- Workflows for scaffolding
  - Scaffold a working directory, Terraform Module, pull request for tfmigrate
- [Update .terraform.lock.hcl automatically](/tfaction/docs/feature/auto-fix)
  - A commit is pushed automatically, so you don't have to update .terraform.lock.hcl yourself
- [Format Terraform Configuration automatically](/tfaction/docs/feature/auto-fix)
  - A commit is pushed automatically, so you don't have to format Terraform configuration yourself
- [Drift Detection](/tfaction/docs/feature/drift-detection)
  - Detect the drift periodically and manage the drift as GitHub Issues

[Dynamic build matrix for Monorepo](/tfaction/docs/feature/build-matrix)

![image](https://user-images.githubusercontent.com/13323303/151699474-b6cf9927-a0d1-4eb7-85fd-19504432362c.png)

Notify the result of CI to pull requests with [tfcmt](https://github.com/suzuki-shunsuke/tfcmt), [github-comment](https://github.com/suzuki-shunsuke/github-comment), and [reviewdog](https://github.com/reviewdog/reviewdog)

Result of `terraform plan`

![image](https://user-images.githubusercontent.com/13323303/147400233-8b9411d6-0255-4c36-9e9f-35e44223c979.png)

Result of `tfsec`

![image](https://user-images.githubusercontent.com/13323303/153747798-0e6ac3d4-e335-4c20-8e2a-1f5b43205ff3.png)

Result of `trivy`

![image](https://github.com/suzuki-shunsuke/trivy-config-action/assets/13323303/e4d7f6f7-3df3-44bb-8f98-535173ce096e)

Result of `tflint`

![image](https://user-images.githubusercontent.com/13323303/153742833-403ea6c5-a780-4d2a-a30c-3a481c0971b1.png)

Result of `conftest`

![image](https://user-images.githubusercontent.com/13323303/150035710-249c4cbd-47fa-46d7-ae0d-28ab4ace1a64.png)

[Update related pull requests automatically when the remote state is updated](/tfaction/docs/feature/auto-update-related-prs)

![image](https://user-images.githubusercontent.com/13323303/151699327-ba31892c-c4a6-47e7-a944-15fca81dfbfb.png)

[Create a pull request automatically to follow up the apply failure](/tfaction/docs/feature/follow-up-pr)

![image](https://user-images.githubusercontent.com/13323303/151699230-1c109a57-47d1-4c3b-9c3a-4dfec786a043.png)

![image](https://user-images.githubusercontent.com/13323303/151699142-6d19cd51-eac5-4f69-bfe5-7920df69edc6.png)

[Support tfmigrate](/tfaction/docs/feature/tfmigrate)

`tfmigrate plan`

![image](https://user-images.githubusercontent.com/13323303/150029520-fd3aac78-d76a-41ee-9df0-a7fc02fb12b7.png)

`tfmigrate apply`

![image](https://user-images.githubusercontent.com/13323303/150029697-316218e0-cb1e-4a8d-ad5c-0c12e1cb68dc.png)

[Update dependencies by Renovate safely](/tfaction/docs/feature/renovate)

CI fails if there are changes, which enables to merge pull requests without changes safely.

![image](https://user-images.githubusercontent.com/13323303/150064670-2c6a646f-81f2-496f-b69a-873b6469593e.png)

[Update .terraform.lock.hcl automatically](/tfaction/docs/feature/auto-fix)

![image](https://user-images.githubusercontent.com/13323303/155866735-85f964d8-7bb7-411c-9b20-5f7abcea3e1a.png)

--

![image](https://user-images.githubusercontent.com/13323303/155866753-32012a3b-02fe-4f58-935e-178283ae2c77.png)

[Format Terraform Configuration](/tfaction/docs/feature/auto-fix)

![image](https://user-images.githubusercontent.com/13323303/155866979-52dd2e6f-9885-4af1-bac0-abd1280fdea5.png)

--

![image](https://user-images.githubusercontent.com/13323303/155866989-8cbcd50e-4764-4f47-a50f-102d04a04f89.png)

[Drift Detection](/tfaction/docs/feature/drift-detection)

![image](https://user-images.githubusercontent.com/13323303/233079963-68765f2e-1efd-4278-b6c3-145eae9ef9c0.png)

## Blog, Slide

- English
  - [2023-06-05 Terraform's Drift Detection by tfaction](https://dev.to/suzukishunsuke/terraforms-drift-detection-by-tfaction-1dkh)
  - [2022-02-12 tfaction - Build Terraform Workflow with GitHub Actions](https://speakerdeck.com/szksh/tfaction-build-terraform-workflow-with-github-actions)
- Japanese
  - [2023-06-05 tfaction による Terraform の Drift Detection](https://zenn.dev/shunsuke_suzuki/articles/tfaction-drift-detection)
  - [2022-03-03 tfaction v0.5.0 の update](https://zenn.dev/shunsuke_suzuki/articles/tfaction-v050)
  - [2022-02-06 tfaction の導入ガイド](https://zenn.dev/shunsuke_suzuki/articles/tfaction-setup)
  - [2022-02-04 Terraform の CI を AWS CodeBuild から GitHub Actions + tfaction に移行しました](https://blog.studysapuri.jp/entry/2022/02/04/080000)
  - [2022-01-24 tfaction - GitHub Actions で良い感じの Terraform Workflow を構築](https://zenn.dev/shunsuke_suzuki/articles/tfaction-introduction)

## Getting Started

https://github.com/suzuki-shunsuke/tfaction-getting-started

## Release Notes

https://github.com/suzuki-shunsuke/tfaction/releases

## Versioning Policy

[suzuki-shunsuke/versioning-policy v0.1.0](https://github.com/suzuki-shunsuke/versioning-policy/blob/v0.1.0/POLICY.md), which is compatible with [Semantic Versioning 2.0.0](https://semver.org/).

## LICENSE

[MIT](https://github.com/suzuki-shunsuke/tfaction/blob/main/LICENSE)
