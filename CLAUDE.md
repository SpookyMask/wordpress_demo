# WordPress demo — Kalin Shekerdzhiev

At session start, read the full owner profile and rules before doing anything else:
- `C:\Coder\AI Operator\coding-with-ai-agents-starter - mine\CLAUDE.md`
- `C:\Coder\AI Operator\coding-with-ai-agents-starter - mine\rules.md`

If they cannot be read, say so and follow the essentials below.

## Essentials

- **Greet me by name** (Kalin Shekerdzhiev) in one short line at session start.
- **Ask before acting.** Explain the plan, wait for my go. Ask before any task likely to cost more than 10 000 tokens.
- **Answers:** detailed, in paragraphs under headings, structured as the steps to take. English throughout.
- **Installs:** only git and web tooling, and only inside this folder. Nothing system-wide: no services,
  no PATH or registry changes, nothing in `C:\xampp` or `Program Files`.
- **Stack:** portable XAMPP (Apache + MariaDB + PHP) inside this folder, WordPress, front-end work in PHP/HTML/CSS/JS.
- **Verify:** Apache and MySQL running in the XAMPP Control Panel, then open `http://localhost/` and see the change.
- **Done:** the change is visible at `http://localhost/` with nothing else broken, and it is committed in git.
- **Git:** one commit per change, English, imperative. Never commit `wp-config.php`, XAMPP binaries, database files or logs.

## Project setup

Everything lives under `C:\Coder\AI Operator\WordPress demo\`. Do one step at a time and confirm with me before each.

1. **Get portable XAMPP.** From https://sourceforge.net/projects/xampp/files/XAMPP%20Windows/ take the newest
   `xampp-portable-windows-x64-<version>.zip` (the .zip, never the .exe installer from apachefriends.org).
2. **Unpack it here**, so the result is `WordPress demo\xampp\`. Run `xampp\setup_xampp.bat` once to fix its paths.
   Do not install Apache or MySQL as Windows services.
3. **Start the servers** with `xampp\xampp-control.exe` → Start Apache and MySQL. If port 80 is taken, stop and
   ask me. Do not change other software to free it.
4. **Clear the web root.** Move XAMPP's default contents of `xampp\htdocs\` into `xampp\htdocs-default\`.
   Move, never delete.
5. **Get WordPress** from https://wordpress.org/latest.zip and unpack its contents directly into `xampp\htdocs\`,
   so `http://localhost/` serves WordPress.
6. **Create the database.** Use `wordpress_demo` (utf8mb4_unicode_ci) through `http://localhost/phpmyadmin/`.
7. **Install WordPress** at `http://localhost/`. Use database `wordpress_demo`, user `root`, an empty password
   (XAMPP default, local only) and host `localhost`. Site credentials are mine to choose. Do not write them in this repo.
8. **Git ignore.** Track this file, `.gitignore` and the whole WordPress folder `xampp/htdocs/` (core, themes,
   plugins, uploads). Ignore the rest of `xampp/`, `wp-config.php`, WordPress temp folders and `*.zip`.
9. **First commit.** Stage files by path, review `git diff --cached`, then commit.

## Day-to-day

- Front-end changes go in a theme under `xampp/htdocs/wp-content/themes/`. Never edit WordPress core files
  (`wp-admin/`, `wp-includes/`). Updates overwrite them.
- After each change: open `http://localhost/` → confirm → commit.
- **Commit every change to the WordPress folder** (`xampp/htdocs/`): one git commit per change, staging by path
  only the files that change touched (see step 8). Before the first commit of a task, ask me which branch to commit to. If that
  branch does not exist, create it (`git switch -c <branch>`); if it does, switch to it. Never commit to a
  branch I have not named.
