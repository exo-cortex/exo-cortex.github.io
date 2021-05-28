---
title: "Github First Use"
date: 2021-05-28T21:52:50+02:00
draft: false
---

How to initialize git repository, add files, commit changes and push to existing github repository:

```bash
echo "# exo-cortex.github.io" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:exo-cortex/exo-cortex.github.io.git
git push -u origin main
```
