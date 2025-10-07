# Copilot Instructions for Academic Pages Codebase

This repository is a Jekyll-based GitHub Pages template for academic and professional portfolio websites. It is forked from the Minimal Mistakes Jekyll Theme and customized for academic use.

## Project Structure & Key Components
- **_config.yml, _config_docker.yml**: Main site configuration. Controls site-wide settings, navigation, and theme options.
- **_data/**: Contains YAML/JSON files for authors, navigation, UI text, and comments. Update these to change site content and structure.
- **_includes/**, **_layouts/**: Jekyll partials and layouts. Use these to customize page structure and reusable components.
- **_pages/**, **_posts/**, **_portfolio/**, **_publications/**, **_talks/**, **_teaching/**: Content directories. Add or edit Markdown files here to update site content.
- **assets/**, **images/**, **files/**: Static assets (CSS, JS, images, downloadable files).
- **markdown_generator/**: Python scripts and Jupyter notebooks for generating Markdown from TSV/CSV data (e.g., publications, talks).
- **Dockerfile, docker-compose.yaml**: For containerized local development.

## Developer Workflows
- **Local Development**:
  - Install dependencies: `sudo apt install ruby-dev ruby-bundler nodejs` (Linux) or use Homebrew on Mac.
  - Install Ruby gems: `bundle install` (use `bundle config set --local path 'vendor/bundle'` if permission errors).
  - Start local server: `jekyll serve -l -H localhost` or `bundle exec jekyll serve -l -H localhost`.
  - Access site at `http://localhost:4000`.
- **Docker Workflow**:
  - Build and run: `chmod -R 777 . && docker compose up`
  - Site available at `http://localhost:4000`.
- **VS Code DevContainer**: Use "Reopen in Container" for a pre-configured environment.

## Project-Specific Conventions
- **Content is organized by type** (posts, pages, portfolio, etc.) in dedicated folders.
- **Configuration-driven navigation and UI**: Update `_data/navigation.yml` and `_data/ui-text.yml` for menus and labels.
- **Custom content generation**: Use scripts in `markdown_generator/` to automate Markdown creation from data files.
- **Minimal Mistakes theme**: Most layouts and includes are inherited; override by copying to local `_layouts/` or `_includes/`.
- **Static files**: Place PDFs and other downloads in `files/` for direct linking.

## Integration Points & External Dependencies
- **Jekyll**: Static site generator. Most logic is in Liquid templates.
- **Ruby gems**: Managed via `Gemfile`.
- **Node.js**: Required for some asset pipelines.
- **Docker**: For cross-platform development.
- **GitHub Pages**: Deploys from the `master` branch.

## Examples
- To add a new publication: Place a Markdown file in `_publications/` or use a script in `markdown_generator/`.
- To customize the homepage: Edit `_pages/about.md` and relevant includes/layouts.
- To update navigation: Edit `_data/navigation.yml`.

## References
- See `README.md` for setup and troubleshooting.
- See `_config.yml` for global settings.
- See `markdown_generator/` for automation scripts.

---
For more, visit https://academicpages.github.io/ or the upstream Minimal Mistakes documentation.
