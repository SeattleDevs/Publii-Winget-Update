# Publii WinGet Auto-Updater

This repository contains a GitHub Actions workflow that automatically updates the [TidyCustoms.Publii](https://winstall.app/apps/TidyCustoms.Publii) package in the [Microsoft WinGet package index](https://github.com/microsoft/winget-pkgs).

## How It Works

- **Daily Check** – The workflow runs daily.
- **Tag Detection** – It fetches the latest release tag from the [GetPublii/Publii](https://github.com/GetPublii/Publii) repository.
- **Manifest Update** – Uses [`wingetcreate`](https://github.com/microsoft/winget-create) to update the manifest with the new version and installer URL.
- **Pull Request** – Submits the updated manifest to winget's repo.

## Requirements

1. **GitHub Personal Access Token (PAT)**
   You need your action to get
   - Create a classic personal github token with repo permissions at https://github.com/settings/personal-access-tokens (fine grained tokens are not supported)
   - Add it to this repo's secrets (**Settings → Secrets and variables → Actions**) as `WINGET_CREATE_GITHUB_TOKEN`.

2. **Workflow File**
   - The workflow file is located at `.github/workflows/publii-update.yml`.

## Usage

- The workflow runs automatically on schedule.
- You can also trigger it manually from the **Actions** tab using the `workflow_dispatch` event.

## License

This project is licensed under the [MIT License](LICENSE).
