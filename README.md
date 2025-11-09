# bradford415.github.io


### Running the site locally
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
   jekyll serve -l -H localhost
   ```
