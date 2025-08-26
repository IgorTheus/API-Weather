# Weather API - Consulta de Clima com Node.js

Este projeto é uma API REST simples feita com Node.js, Express e Axios, que consome dados da OpenWeatherMap API para retornar informações do clima atual de cidades no mundo todo.

# Funcionalidades

Consulta do clima de uma cidade específica (/weather)

Consulta do clima de múltiplas cidades (/multiple)

Alerta de temperatura baseado na cidade (/alert)

# Requisitos

Antes de rodar o projeto, você precisa ter instalado:

Node.js
npm (instalado junto com o Node)

# Clone o repositório:
`
git clone https://github.com/seu-usuario/seu-repositorio.git
cd seu-repositorio`


Instale as dependências:

Execute o seguinte comando para instalar as dependências:

npm install


Inicie o servidor:

Após instalar as dependências, execute o servidor com:

node index.js


O servidor será iniciado e estará disponível em http://localhost:3000.

API Key

Este projeto utiliza a OpenWeatherMap API. Você devera criar uma conta no site deles e gerar uma chave

Rotas Disponíveis

🔹 /weather

Consulta o clima atual de uma cidade específica.

Parâmetros (query):

city: Nome da cidade (ex: Sao Paulo)

country: Código do país (ex: BR)

Exemplo:
http://localhost:3000/weather?city=Sao Paulo&country=BR

🔹 /multiple

Consulta o clima de múltiplas cidades de uma só vez.

Parâmetro (query):

cities: Lista de cidades separadas por vírgulas (ex: Sao Paulo,Rio de Janeiro,Belo Horizonte)

Exemplo:
http://localhost:3000/multiple?cities=Sao Paulo,Rio de Janeiro,Belo Horizonte

🔹 /alert

Retorna um alerta de temperatura baseado na cidade consultada:

Temperatura > 30°C → Quente

Temperatura < 10°C → Frio

Temperatura entre 10°C e 30°C → Agradável

Parâmetros (query):

city: Nome da cidade

country: Código do país

Exemplo:
http://localhost:3000/alert?city=Curitiba&country=BR

Estrutura do Código

Aqui está um breve resumo de como o código está organizado:

Express é utilizado para criar o servidor e lidar com as rotas.

Axios é usado para fazer as requisições à API da OpenWeatherMap.

CORS é ativado para permitir que o servidor seja acessado de diferentes origens.

O código possui três rotas principais:

/weather: Para consultar o clima de uma única cidade.

/multiple: Para consultar o clima de várias cidades.

/alert: Para gerar um alerta de temperatura com base na cidade.
