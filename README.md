# How to Use Skills from skill_pub in a New Codespace

## Prerequisites
- A new repo opened in GitHub Codespaces
- `skill_pub` is public: `https://github.com/6110-CTO/skill_pub`

---

## Steps

### 1. Pull CLAUDE.md into your repo root
```bash
curl -O https://raw.githubusercontent.com/6110-CTO/skill_pub/main/CLAUDE.md
```

### 2. Pull and extract the skill
```bash
mkdir -p skills && cd skills
curl -L -O https://github.com/6110-CTO/skill_pub/raw/main/<skill-name>.skill
unzip <skill-name>.skill
rm <skill-name>.skill
cd ..
```

### 3. Verify
```bash
find skills
```
Expected output:
```
skills/<skill-name>/SKILL.md
```

### 4. Commit
```bash
git add .
git commit -m "add <skill-name> skill"
git push
```

---

## Available Skills

| Skill | Triggers |
|---|---|
| `mlops-sanitary-environment` | uv, pyproject.toml, Ruff, Pyright, pre-commit, ADR, src layout |
