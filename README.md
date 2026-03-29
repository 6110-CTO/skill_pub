# skill_pub

## About

Claude Skills are instruction files that teach Claude how to complete specific tasks according to your team's standards. When a skill is present in your project, Claude reads it automatically and follows its guidelines — no need to explain the process every time.

This repo (`skill_pub`) is a shared library of skills. Each skill is a self-contained file that you pull into any new project in minutes.

---

## Steps

### 1. Create a new repo
1. Go to `https://github.com/new`
2. Give it your project name
3. Check **Add a README file**
4. Click **Create repository**

### 2. Open a Codespace
1. Click the green **Code** button
2. Go to the **Codespaces** tab
3. Click **Create codespace on main**

### 3. Install Claude Code extension
1. Click the **Extensions** icon in the left sidebar (`Ctrl+Shift+X`)
2. Search for **Claude Code**
3. Click **Install**

### 4. Pull CLAUDE.md into your repo root
```bash
curl -O https://raw.githubusercontent.com/6110-CTO/skill_pub/main/CLAUDE.md
```

### 5. Pull and extract the skill
```bash
mkdir -p skills && cd skills
curl -L -O https://github.com/6110-CTO/skill_pub/raw/main/<skill-name>.skill
unzip <skill-name>.skill
rm <skill-name>.skill
cd ..
```

### 6. Verify
```bash
find skills
```
Expected output:
```
skills/<skill-name>/SKILL.md
```

### 7. Commit
```bash
git add .
git commit -m "add <skill-name> skill"
git push
```

---

## Running a Skill

Open the Claude Code panel and use this prompt:
```
Set up a complete production-ready MLOps Python project environment. Follow the skill instructions end to end and complete all tasks until the Definition of Done is fully checked off. Don't stop between steps — just do it.
```

---

## Available Skills

| Skill | Triggers |
|---|---|
| `mlops-sanitary-environment` | uv, pyproject.toml, Ruff, Pyright, pre-commit, ADR, src layout |
