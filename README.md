# Hashtag Generator API

API Minimal construída em .NET 9 para geração de hashtags dinâmicas utilizando modelos de IA locais via Ollama. Permite consumir diferentes modelos do Ollama para sugerir N hashtags a partir de um tema, com documentação e testes via Swagger.

## Funcionalidades

- Gera hashtags exclusivas seguindo regras definidas no prompt (sem espaços, sem duplicatas).
- Permite escolher o modelo local Ollama na chamada (campo `model`).
- Salva o histórico em memória de todas as hashtags já geradas na execução do servidor.
- Documentação interativa e testes rápidos em `/swagger`.

## Pré-requisitos

- [.NET 9 SDK](https://dotnet.microsoft.com/download)
- [Ollama](https://ollama.com/) instalado e rodando localmente  
- Pelo menos um modelo Ollama baixado para uso (veja abaixo)

## Instalação e Configuração

1. **Clone o repositório**

- git clone https://github.com/NathanMagno/Hashtag-Generator.git
- cd hashtag-generator-api


2. **Restaure as dependências**

dotnet restore

3. **Instale o Ollama na sua máquina**
- Baixe em: [https://ollama.com/](https://ollama.com/)

4. **Baixe um modelo no Ollama**

- ollama pull <Nome do modelo que você escolheu>

5. **Inicie o Ollama**

- O serviço ficará ouvindo em `http://localhost:11434`.

6. **Inicie a API**

- dotnet run

- Acesse os testes/documentação em [http://localhost:5167/swagger]

- Use o endpoint GET `/hashtags` para ver todas as hashtags criadas no servidor enquanto ele roda.

- Use o endpoint POST `/hashtags` para gerar novas hashtags a partir de textos

**Formato JSON que deve ser enviado:**
~~~json
{
"text": "campeonato de futebol no Brasil",
"count": 7,
"model": "llama3.2:3b"
}
~~~

Desenvolvido por Nathan Magno Gustavo Cônsolo
