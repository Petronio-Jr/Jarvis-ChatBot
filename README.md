# JARVIS — IA Avançada

Chatbot web com a persona do JARVIS, o assistente pessoal do Homem de Ferro. É uma super inteligência artificial com jeito de mordomo britânico: formal, cortês, com ironia fina e conhecimento profundo de cultura nerd/geek (games, RPG, quadrinhos, animações, filmes e séries). Toda resposta termina com a palavra `cambio`.

Projeto desenvolvido no Workshop da Computação 2026.

## Tecnologias

- Python + Flask (servidor web)
- Amazon Bedrock via boto3 (geração das respostas)
- Modelo: Claude Haiku 4.5 (`us.anthropic.claude-haiku-4-5-20251001-v1:0`), região `us-east-1`
- Interface em HTML, CSS e JavaScript puro, com visual futurista e holográfico

## Funcionalidades

- Interface de chat em tela cheia, responsiva para celular
- Memória de conversa: o histórico é mantido e enviado ao modelo a cada pergunta
- Reconhece sarcasmo e pedidos lúdicos e responde no clima da cultura nerd
- Respostas curtas, em um parágrafo, encerradas com `cambio`

## Pré-requisitos

- Python 3
- Credenciais AWS com acesso ao Amazon Bedrock, definidas por variáveis de ambiente:

```bash
export AWS_ACCESS_KEY_ID=...
export AWS_SECRET_ACCESS_KEY=...
# opcional, se usar credenciais temporárias:
export AWS_SESSION_TOKEN=...
```

As credenciais nunca ficam escritas no código.

## Como rodar

```bash
pip install -r requirements.txt
python app.py
```

Depois acesse `http://localhost:5000` no navegador.

## Rotas

- `GET /` — exibe a página de chat.
- `POST /chat` — recebe `{"message": "..."}` e devolve `{"reply": "..."}`. Mensagem vazia retorna erro 400.

## Estrutura do projeto

```
.
├── app.py              # Aplicação Flask e integração com o Bedrock
├── requirements.txt    # Dependências (flask, boto3)
└── templates/
    └── index.html      # Interface de chat
```
