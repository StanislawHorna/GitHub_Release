# 📦 Check GitHub Release

This GitHub composite action checks a **GitHub Release** and **git tag** existence for the current repository.
If it is missing one of them action fails

## Inputs

| Name          | Description                            | Required | Default |
| ------------- | -------------------------------------- | -------- | ------- |
| `GH_TOKEN`    | GitHub token with `repo` access        | ✅ Yes   | –       |
| `release_tag` | (Optional) Explicit release tag to use | ✅ Yes   | -       |

---


---

## 🚀 Usage

```yaml
jobs:
  create-release:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v6

      - name: Check GitHub Release
        uses: StanislawHornaGitHub/GitHub_Release/check-release@main
        with:
          GH_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          release_tag: '1.0.0'
```
