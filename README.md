# Site Link: [bradford415.github.io](https://bradford415.github.io)

## Running the site locally
Running the site locally is essential to modify your website and see the changes before pushing your edits to the internet

1. Clone the repository
1. Install the necessary libraries
    ```bash
    # linux
    sudo apt install ruby-dev ruby-bundler nodejs
    ```
  
    ```bash
    # mac
    brew install rbenv ruby-build
    rbenv install 3.2.2
    export PATH="$HOME/.rbenv/bin:$PATH"
    brew install node
    gem install bundler
    
    ```
1. Run `bundle install` to install ruby dependencies. If you get errors, delete Gemfile.lock and try again.
    ```bash
    bundle config set --local path 'vendor/bundle'
    bundle install
    ```
1. Generate the HTML and serve it from `localhost:4000` the local server will automatically rebuild and refresh the pages on change to Markdown (*.md) and HTML files, while changes to the core template and configuration (i.e., _config.yml) will require stopping and restarting Jekyll
   ```bash
   # `exec` uses only the local version in the gem.lock file instead of global system versions
   bundle exec jekyll serve -l -H localhost 
   ```

## Editing the site

### Main pages
* Home page/about me: `_pages/about.md`
* Navigation bar: `_data/navigation.yml`
* Portfolio items: `_portfolio/`

### Notes
* `jekyll serve` will automatically rebuild and update changes to `*.md` and `*.html` files; any other changes will require restarting the server. Therefore, all you should have to do to edit the site is modify the `.md` and `.html` files.
* When creating new pages in the navbar that require looping through other files (like portfolio), you need to:
  * update ALL locations in `_config.yml` (collections and scope)
  * update the `navigation.yml`
  * create its respective folder with `.md` files `_newpagedir/`     
* Files in `_site/` are regenerated every time you run your site, so do not modify these
* If certain files don't refresh or upload, like your profile picture, after restarting the site, try doing a hard refresh in the browser (Mac: `Cmd + Shift + R`, Windows: `Ctrl + Shift + R`) so that the browser ignores the cache


