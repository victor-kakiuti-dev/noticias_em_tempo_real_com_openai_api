# 🗞️ Chatbot de Notícias com IA

Um chatbot inteligente que busca e resume notícias da internet utilizando web scraping e a API da OpenAI. O assistente mantém histórico de conversação e pode tanto buscar notícias de sites específicos quanto conversar normalmente.

## ✨ Funcionalidades

- 🔍 **Web Scraping Inteligente**: Extrai conteúdo de páginas de notícias
- 🤖 **Resumo Automático**: Usa GPT-4o-mini para criar resumos claros e objetivos
- 💬 **Conversação Natural**: Mantém histórico e contexto da conversa
- 🔗 **Análise de Links**: Identifica automaticamente links relevantes de notícias
- 🎨 **Interface Amigável**: Interface web moderna usando Gradio
- 🛡️ **Tratamento de Erros**: Lida com sites que bloqueiam scraping

## 🚀 Como Usar

### Pré-requisitos

- Python 3.8+
- Chave de API da OpenAI

### Instalação

1. Clone o repositório:
```bash
git clone victor-kakiuti-dev\noticias_em_tempo_real_com_openai_api.git
cd chatbot-noticias
```

2. Instale as dependências:
```bash
pip install openai gradio requests beautifulsoup4 python-dotenv
```

3. Configure sua chave da API:

Crie um arquivo `.env` na raiz do projeto:
```env
OPENAI_API_KEY=sua-chave-aqui
```

4. Execute o aplicativo:
```bash
python app.py
```

5. Acesse no navegador:
```
http://localhost:7860
```

## 💡 Exemplos de Uso

### Buscar Notícias
```
"Busque as últimas notícias de https://www.bbc.com/portuguese"
"Resuma as notícias de https://www.metropoles.com"
"O que está acontecendo em https://www.dw.com/pt-br"
```

### Conversação Normal
```
"O que você pode fazer?"
"Qual a diferença entre web scraping e API?"
"Me explique sobre inteligência artificial"
```

## 🌐 Sites Recomendados

### Funcionam Bem ✅
- BBC Brasil: `https://www.bbc.com/portuguese`
- DW Brasil: `https://www.dw.com/pt-br`
- Metrópoles: `https://www.metropoles.com`
- UOL Notícias: `https://noticias.uol.com.br`
- Estadão: `https://www.estadao.com.br`

### Podem Ter Restrições ⚠️
- G1 (proteção anti-scraping forte)
- Folha de S.Paulo (paywall)
- Sites com muito JavaScript

## 🏗️ Arquitetura

```
┌─────────────┐
│   Usuário   │
└──────┬──────┘
       │
       v
┌─────────────────┐
│  Gradio Chat    │
│   Interface     │
└──────┬──────────┘
       │
       v
┌─────────────────┐
│  OpenAI GPT-4   │
│  Function Call  │
└──────┬──────────┘
       │
       v
┌─────────────────┐
│  Web Scraping   │
│  BeautifulSoup  │
└──────┬──────────┘
       │
       v
┌─────────────────┐
│  Site Notícias  │
└─────────────────┘
```



## 🔧 Tecnologias Utilizadas

- **OpenAI GPT-4o-mini**: Modelo de linguagem para conversação e resumos
- **Gradio**: Interface web interativa
- **BeautifulSoup4**: Web scraping e parsing de HTML
- **Requests**: Requisições HTTP
- **Python-dotenv**: Gerenciamento de variáveis de ambiente

## ⚙️ Configurações

### Limites e Ajustes

No código você pode ajustar:

```python
MODEL = "gpt-4o-mini"  # Modelo da OpenAI
timeout=15             # Timeout das requisições (segundos)
[:8000]               # Limite de caracteres do conteúdo
[:3]                  # Número máximo de links analisados
```

### Headers HTTP

O código usa headers personalizados para evitar bloqueios:
```python
enhanced_headers = {
    "User-Agent": "Mozilla/5.0...",
    "Accept-Language": "pt-BR,pt;q=0.9",
    # ...
}
```

## 🛡️ Limitações

- Sites com forte proteção anti-scraping podem bloquear o acesso
- Conteúdo carregado via JavaScript não é capturado
- Sites com paywall não são acessíveis
- Respeite os `robots.txt` e termos de uso dos sites

## 🤝 Contribuindo

Contribuições são bem-vindas! Sinta-se à vontade para:

1. Fazer fork do projeto
2. Criar uma branch para sua feature (`git checkout -b feature/NovaFuncionalidade`)
3. Commit suas mudanças (`git commit -m 'Adiciona nova funcionalidade'`)
4. Push para a branch (`git push origin feature/NovaFuncionalidade`)
5. Abrir um Pull Request

## 📝 Licença

Este projeto está sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.

## ⚠️ Aviso Legal

Este projeto é apenas para fins educacionais. Sempre respeite:
- Termos de uso dos sites
- Políticas de robots.txt
- Leis de direitos autorais
- Rate limits e políticas anti-scraping

## 👤 Autor

Seu Nome
- GitHub: [@victor-kakiuti-dev](https://github.com/victor-kakiuti-dev)
- LinkedIn: [Victor Kakiuti Boer](https://linkedin.com/in/seu-perfil)



⭐ Se este projeto foi útil, considere dar uma estrela no GitHub!