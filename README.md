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
cd seu-repositorio
`


# Instale as dependências:

Execute o seguinte comando para instalar as dependências:

`
npm install express axios cors
`

Inicie o servidor:

`
node index.js
`

O servidor será iniciado e estará disponível em http://localhost:3000.

# API Key

Este projeto utiliza a OpenWeatherMap API. Você devera criar uma conta no site deles e gerar uma chave

# O código possui três rotas principais:

/weather: Para consultar o clima de uma única cidade.

/multiple: Para consultar o clima de várias cidades.

/alert: Para gerar um alerta de temperatura com base na cidade.

# 🔹 /weather

Consulta o clima atual de uma cidade específica.

Parâmetros (query):

city: Nome da cidade (ex: Campinas)

country: Código do país (ex: BR)

Exemplo de input:
http://localhost:3000/weather?city=Campinas&country=BR

Exemplo de output:
`
{
  "temperature": 20.89,<br></br>
  "humidity": 78,
  "windSpeed": 24.084000000000003,
  "rainChance": 0,
  "weatherCondition": "céu limpo"
}
`

# 🔹 /multiple

Consulta o clima de múltiplas cidades de uma só vez.

Parâmetro (query):

cities: Lista de cidades separadas por vírgulas (ex: Campinas, Valinhos e Indaiatuba)

Exemplo de input:
http://localhost:3000/multiple?cities=Campinas,Valinhos,Indaiatuba

Exemplo de output:
`
[
  {
    "city": "Campinas",
    "temperature": 19.89,
    "weather": "céu limpo"
  },
  {
    "city": "Valinhos",
    "temperature": 19.87,
    "weather": "céu limpo"
  },
  {
    "city": "Indaiatuba",
    "temperature": 20.3,
    "weather": "céu limpo"
  }
]
`

# 🔹 /alert

Retorna um alerta de temperatura baseado na cidade consultada:

Temperatura > 30°C → Quente

Temperatura < 10°C → Frio

Temperatura entre 10°C e 30°C → Agradável

Parâmetros (query):

city: Nome da cidade

country: Código do país

Exemplo de input:
http://localhost:3000/alert?city=Curitiba&country=BR

Exemplo de output:
`
{
  "city": "Curitiba",
  "temperature": 15.46,
  "alert": "Agradavel"
}
`
