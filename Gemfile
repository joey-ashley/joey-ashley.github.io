# ============================================================
# Gemfile
# ------------------------------------------------------------
# Ruby dependencies for local Jekyll development.
#
# Quick start:
#   1. Install Ruby (3.1+ recommended). On macOS: `brew install ruby`.
#      On Ubuntu: `sudo apt install ruby-full build-essential`.
#   2. Install Bundler:        gem install bundler
#   3. Install dependencies:   bundle install
#   4. Run the site locally:   bundle exec jekyll serve
#   5. Open http://localhost:4000
#
# Note: GitHub Pages builds your site server-side using its own
# pinned versions of Jekyll and plugins. The `github-pages` gem
# below mirrors that environment locally so what you see in
# development matches what gets deployed.
# ============================================================

source "https://rubygems.org"

# ------------------------------------------------------------
# GitHub Pages
# ------------------------------------------------------------
# This gem bundles Jekyll plus every plugin GitHub Pages supports,
# all pinned to the exact versions GitHub uses to build your site.
# Don't add `gem "jekyll"` separately — it's already included here
# and pinning it yourself will cause version conflicts.
gem "github-pages", group: :jekyll_plugins

# ------------------------------------------------------------
# Plugins
# ------------------------------------------------------------
# Must match the `plugins:` list in _config.yml. Listing them here
# lets `bundle exec jekyll serve` find them locally.
group :jekyll_plugins do
  gem "jekyll-feed"
  gem "jekyll-seo-tag"
  gem "jekyll-sitemap"
  gem "jekyll-remote-theme"
end

# ------------------------------------------------------------
# Platform-specific gems
# ------------------------------------------------------------
# Performance booster for file watching on macOS during `jekyll serve`.
# Harmless on other platforms; the install: directive scopes it.
gem "wdm", "~> 0.1.1", :install_if => Gem.win_platform?

# tzinfo-data is required on Windows and JRuby, where the OS doesn't
# provide a system timezone database. Safe to include unconditionally.
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end

# Ruby 3.0+ removed `webrick` from the standard library, but Jekyll's
# built-in dev server still depends on it. Adding it explicitly keeps
# `jekyll serve` working on modern Ruby.
gem "webrick", "~> 1.8"

# ------------------------------------------------------------
# Optional: development-only tools
# ------------------------------------------------------------
# Uncomment if you want them.
#
# group :development do
#   gem "html-proofer"   # Catches broken links & bad HTML in the built site
# end
