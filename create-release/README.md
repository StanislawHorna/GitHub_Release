# 📦 Create GitHub Release

This GitHub composite action creates a **GitHub Release** for the current repository.
If no tag is provided,

it automatically determines the next available version tag using the [`get-release-tag`](/get-release-tag/) action.

## Inputs

| Name          | Description                            | Required | Default                                                     |
| ------------- | -------------------------------------- | -------- | ----------------------------------------------------------- |
| `GH_TOKEN`    | GitHub token with `repo` access        | ✅ Yes   | –                                                           |
| `release_tag` | (Optional) Explicit release tag to use | ❌ No    | if not provided runs [`get-release-tag`](/get-release-tag/) |

---

## Outputs

| Name  | Description              |
| ----- | ------------------------ |
| `tag` | The tag used for release |

---

## 🚀 Usage

```yaml
jobs:
  create-release:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3

      - name: Create GitHub Release
        uses: StanislawHorna/GitHub_Release/create-release@main
        with:
          GH_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```
