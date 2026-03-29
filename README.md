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

### 2. Clone only the skill you need
```bash
git clone --depth=1 --filter=blob:none --sparse https://github.com/6110-CTO/skill_pub.git tmp-skills
```

### 3. Extract and place it
```bash
mkdir -p skills
mv tmp-skills/<skill-name>.skill skills/
cd skills
unzip <skill-name>.skill
rm <skill-name>.skill
cd ..
```

### 4. Clean up
```bash
rm -rf tmp-skills
```

### 5. Verify
```bash
find skills
```
Expected output:
```
skills/<skill-name>/SKILL.md
```

### 6. Commit
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
