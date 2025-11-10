# bradford415.github.io

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
   bundle exec jekyll serve -l -H localhost # `exec` uses only the local version in the gem.lock file instead of global system versions 
   ```

## Editing the site
`jekyll serve` will automatically rebuild and update changes to `*.md` and `*.html` files; any other changes will require restarting the server. Therefore, all you should have to do to edit the site is modify the `.md` and `.html` files.
