# 🔖 Get Release Tag

This GitHub Action generates the **next available version tag**
following a standardized format based on the current ISO week of the year.
It is designed for automated versioning in continuous delivery pipelines.

---

## Tag Format

Tags follow the format: `YY.ww.N`

- `YY` — Last two digits of the current year (e.g., `25` for 2025)
- `ww` — ISO week number (01–53)
- `N` — Incremental release number within that ISO week

For example, the first release in week 32 of 2025 will be: `25.32.0`, the second `25.32.1`, and so on.

## Inputs

| Name       | Description                                             | Required |
| ---------- | ------------------------------------------------------- | -------- |
| `GH_TOKEN` | GitHub token (with `repo` scope) to query existing tags | ✅ Yes   |

## Outputs

| Name  | Description                                      |
| ----- | ------------------------------------------------ |
| `tag` | The next available version tag (e.g., `25.32.1`) |

---

## 🚀 Usage

```yaml
jobs:
  find-tag:
    runs-on: ubuntu-latest
    steps:
      - name: Get Next Release Tag
        id: version
        uses: StanislawHornaGitHub/GitHub_Release/get-release-tag@main
        with:
          GH_TOKEN: ${{ secrets.GITHUB_TOKEN }}

      - name: Display Version
        run: echo "Next version tag is ${{ steps.version.outputs.tag }}"
```
