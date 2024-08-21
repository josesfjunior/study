# Use a imagem oficial do Elixir
FROM elixir:1.17.2-otp-27

# Instale as dependências do sistema operacional necessárias
RUN curl -fsSL https://deb.nodesource.com/setup_21.x | bash - && \
    apt-get install -y nodejs

# Configure o ambiente de trabalho
WORKDIR /app

# Copie o código da aplicação para o contêiner
COPY . .

RUN mix local.hex --force && \
    mix local.rebar --force && \
    mix deps.get


# Exponha a porta onde o Phoenix estará rodando
EXPOSE 4000

# Comando para iniciar o servidor Phoenix no ambiente de desenvolvimento
CMD ["sh", "-c", "mix deps.get &&  mix ecto.migrate && mix phx.server"]
