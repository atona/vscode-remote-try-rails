# Try Out Development Containers: Ruby on Rails

This is a sample project that lets you try out the **[VS Code Remote - Containers](https://aka.ms/vscode-remote/containers)** extension in a few easy steps.

> **Note:** If you're following the quick start, you can jump to the [Things to try](#things-to-try) section. 

## Setting up the development container

Follow these steps to open this sample in a container:

 1. If this is your first time using a development container, please follow the getting started steps.

 2. if you're not yet in a development container:
    - Clone this repository
    - Press <kbd>F1</kbd> and select the **Remote-Containers: Open Folder in Container....** command. 

## Thing to try

One you have this sample opened in a container, you'll be able to work with it like you would locally.

Some things to try:
 1. **Terminal:** Press <kbd>ctrl</kbd> + <kbd>shift</kbd> + <kbd> ^ </kbd> and type `rails new . -d postgresql`

 2. **Edit:**
    - Open `Gemfile`
    - Uncomment on line 17
      ```diff
      - # gem 'mini_racer', platforms: :ruby
      + gem 'mini_racer', platforms: :ruby
      ```
    - Open `config/database.yml`
    - Paste on this code.
      ```yml
      default: &default
        adapter: postgresql
        encoding: unicode
        pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>
        host: <%= ENV.fetch('DATABASE_HOST') { 'localhost' } %>
        port: <%= ENV.fetch('DATABASE_PORT') { 5432 } %>
        username: <%= ENV.fetch('DATABASE_USER') { 'root' } %>
        password: <%= ENV.fetch('DATABASE_PASSWORD') { 'password' } %>

      development:
        <<: *default
        database: app_development

      test:
        <<: *default
        database: app_test

      production:
        <<: *default
        database: app_production
        username: app
        password: <%= ENV['MYAPP_DATABASE_PASSWORD'] %>
      ```
 3. **Run**
    - Type `bundle install` from the terminal window.
    - Type `rails db:create` from the terminal window.
    - Type `rails s -b 0.0.0.0` from the terminal window.
    - Then open a local browser and go to `http://localhost:3000` and note you can connect to the Ruby on Rails App in the container.

## Contributing

This project welcomes contributions and suggestions.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## License

Licensed under the MIT License. See LICENSE in the project root for license information.