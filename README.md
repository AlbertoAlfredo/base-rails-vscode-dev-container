Salve essa pasta na base de seu projeto em branco, mude o nome da pasta para .devcontainer e no vscode use os comandos de devcontainer para reabrir o projeto dentro do container, assim como mágica os containers do ruby e postgresql irão ser criados, e um projeto novo do rails irá ser criado em seguida.

Após isso  

vá até a pasta config e dentro dela no arquivo database.yml e troque todo o código por este: 

```

# PostgreSQL. Versions 9.3 and up are supported.
#
# Install the pg driver:
#   gem install pg
# On macOS with Homebrew:
#   gem install pg -- --with-pg-config=/usr/local/bin/pg_config
# On Windows:
#   gem install pg
#       Choose the win32 build.
#       Install PostgreSQL and put its /bin directory on your path.
#
# Configure Using Gemfile
# gem "pg"
#
default: &default
  adapter: postgresql
  encoding: unicode
  # For details on connection pooling, see Rails configuration guide
  # https://guides.rubyonrails.org/configuring.html#database-pooling
  pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>

development:
  <<: *default
  database: dev_dio

  # The specified database role being used to connect to PostgreSQL.
  # To create additional roles in PostgreSQL see `$ createuser --help`.
  # When left blank, PostgreSQL will use the default role. This is
  # the same name as the operating system user running Rails.
  # username: postgres

  # The password associated with the PostgreSQL role (username).
  # password: postgres
 
  # Connect on a TCP socket. Omitted by default since the client uses a
  # domain socket that doesn't need configuration. Windows does not have
  # domain sockets, so uncomment these lines.
  host: host.docker.internal

  # The TCP port the server listens on. Defaults to 5432.
  # If your server runs on a different port number, change accordingly.
  port: 5432

  # Schema search path. The server defaults to $user,public
  #schema_search_path: myapp,sharedapp,public

  # Minimum log levels, in increasing order:
  #   debug5, debug4, debug3, debug2, debug1,
  #   log, notice, warning, error, fatal, and panic
  # Defaults to warning.
  #min_messages: notice

# Warning: The database defined as "test" will be erased and
# re-generated from your development database when you run "rake".
# Do not set this db to the same as development or production.
test:
  <<: *default
  database: teste_dio

# As with config/credentials.yml, you never want to store sensitive information,
# like your database password, in your source code. If your source code is
# ever seen by anyone, they now have access to your database.
#
# Instead, provide the password or a full connection URL as an environment
# variable when you boot the app. For example:
#
#   DATABASE_URL="postgres://myuser:mypass@localhost/somedatabase"
#
# If the connection URL is provided in the special DATABASE_URL environment
# variable, Rails will automatically merge its configuration values on top of
# the values provided in this file. Alternatively, you can specify a connection
# URL environment variable explicitly:
#
#   production:
#     url: <%= ENV["MY_APP_DATABASE_URL"] %>
#
# Read https://guides.rubyonrails.org/configuring.html#configuring-a-database
# for a full overview on how database connection configuration can be specified.
#
production:
  <<: *default
  database: production_dio
  username: postgres
  password: postgres
  #password: <%= ENV["DIO_DA_ARQUITETURA_AO_DEPLOY_RONRAILS_DATABASE_PASSWORD"] %>


```
