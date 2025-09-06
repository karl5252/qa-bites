
# QA Bites – Blog Dev Environment

Welcome to the development setup for the QA Bites blog built with Jekyll.  
This guide shows you how to run the blog locally for editing, testing, and previewing posts.

## ⚙️ Requirements

- Ruby (version ~3.0+ recommended)
- Bundler (`gem install bundler`)
- Git (to clone the repo, obviously)

On Ubuntu/Debian:

```bash
sudo apt install ruby-full build-essential zlib1g-dev git
````

On macOS (via Homebrew):

```bash
brew install ruby
```

> 💡 If `ruby -v` still shows an old version, add this to `.zshrc` or `.bashrc`:
>
> ```bash
> export PATH=\"/opt/homebrew/opt/ruby/bin:$PATH\"
> ```

---

## 🚀 Getting Started

1. **Clone the repo**

   ```bash
   git clone https://github.com/karl5252/qa-bites.git
   cd qa-bites
   ```

2. **Install dependencies**

   ```bash
   bundle install
   ```

3. **Run the site locally**

   ```bash
   bundle exec jekyll serve
   ```

4. **Preview it in browser**
   Open [http://127.0.0.1:4000](http://127.0.0.1:4000)

---

## 🛠 Common Issues

* ❌ `Could not locate Gemfile or .bundle/ directory`
  → You're not in the project root folder.

* ❌ `jekyll: command not found`
  → Make sure Ruby and Bundler are installed properly. Run:

  ```bash
  gem install jekyll bundler
  ```

---

## 🧪 Workflow Tips

* Posts live in `_posts/` with naming format: `YYYY-MM-DD-title.md`
* Use `lang:` in front matter to organize posts (`en`, `pl`, etc.)
* To rebuild instantly on changes, leave `jekyll serve` running
* Keep assets in `/assets` and use relative paths

---

## 📦 Deploying

Blog is deployed via GitHub Pages at:

🔗 [https://karl5252.github.io/qa-bites/](https://karl5252.github.io/qa-bites/)

GitHub Pages uses the same `jekyll` engine – just push changes to `main` and it updates automatically.

---

Happy writing & testing 🧪✍️
