# 📄 resume

> My resume, written in LaTeX. Every push to `main` automatically compiles and releases a fresh PDF.

![Build](https://github.com/4-sai/resume/actions/workflows/build.yml/badge.svg)
![Release](https://img.shields.io/github/v/release/4-sai/resume?label=latest&color=89b4fa)

---

## ⬇️ Download Latest PDF

**[→ resume.pdf (latest)](https://github.com/4-sai/resume/releases/latest/download/resume.pdf)**

This link **always** points to the most recent compiled version.

---

## 🔄 How it works

```
Edit resume.tex → git push → GitHub Actions compiles PDF → auto-released
```

1. `resume.tex` is the single source of truth
2. On every push to `main`, a GitHub Actions workflow runs
3. LaTeX compiles the PDF using TeX Live
4. A new GitHub Release is created with the PDF attached
5. The `latest` release link always serves the freshest version


---

## 🛠️ Build locally

```bash
# Requires: texlive-full + fontawesome5
pdflatex resume.tex

# Or with Docker (no local LaTeX install needed)
docker run --rm -v "$PWD":/workspace -w /workspace \
  texlive/texlive:latest \
  pdflatex resume.tex
```

---

## 📁 Structure

```
resume/
├── resume.tex                  # Source — edit this
├── .github/
│   └── workflows/
│       └── build.yml           # CI: compile + release
└── README.md
```
