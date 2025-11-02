# 🤖 Projeto: Chatbot de Estudos com Azure AI Foundry

Este projeto é um assistente de estudos pessoal (chatbot) criado para auxiliar na revisão e aprendizado do conteúdo de Programação para Dispositivos Móveis da faculdade.

Utilizando os serviços do **Azure AI Foundry**, o chatbot foi "treinado" com todos os materiais de aula (PDFs) referentes ao bimestre atual, permitindo fazer consultas em linguagem natural sobre o conteúdo.

## 🎯 O Objetivo

O objetivo principal deste projeto é criar uma ferramenta de estudo centralizada e inteligente. Em vez de pesquisar manualmente em dezenas de arquivos PDF por um conceito ou resposta, posso simplesmente perguntar ao chatbot.

Isso otimiza meu tempo de estudo, me ajuda a encontrar informações rapidamente e serve como um "tutor virtual" que tem como base exclusivamente o material fornecido pelos professores.

## 🛠️ Tecnologias Utilizadas

* **Azure AI Foundry:** Plataforma central para a criação e gerenciamento do agente de IA.
* **Azure AI Studio (Recurso "Chat com seus dados"):** Utilizado para conectar a fonte de dados (PDFs) ao modelo de linguagem.
* **Azure AI Search (antigo Cognitive Search):** O serviço de backend que indexa todo o conteúdo dos documentos PDF, permitindo a busca e recuperação de informações relevantes (técnica conhecida como RAG - Retrieval-Augmented Generation).
* **Modelo de IA (GPT-5o):** O modelo de linguagem que entende as perguntas do usuário e gera as respostas com base nos dados recuperados.

## 📖 Como Funciona

O fluxo de trabalho para a criação deste assistente foi o seguinte:

1.  **Criação do Projeto:** O projeto foi iniciado dentro do hub do Azure AI Foundry.
2.  **Upload dos Dados:** Todos os materiais de estudo do bimestre em formato PDF (slides de aula, artigos, notas, listas de exercícios) foram carregados e vinculados ao projeto.
3.  **Indexação:** O Azure AI Search processou automaticamente todos os documentos, quebrando-os em "chunks" (pedaços) e criando um índice de busca para que o conteúdo pudesse ser consultado rapidamente.
4.  **Interação (Playground):** No playground de chat do Azure AI, agora é possível fazer perguntas diretamente.
    * Quando eu faço uma pergunta, o sistema primeiro busca nos meus PDFs as informações mais relevantes sobre o conteudo.
    * Em seguida, ele envia a minha pergunta, junto com os trechos de texto encontrados, para o modelo de IA.
    * O modelo, então, formula uma resposta coesa e precisa, citando as fontes (os PDFs) de onde tirou a informação.

## 🚀 Exemplos de Uso

Algumas das perguntas que o chatbot é capaz de responder:

* `"Me explique o conceito de Activity"`
* `"Faça um resumo sobre Interface gráfica"`
* `"Quais são os pontos principais que o professor mencionou sobre Intent?"`


## 💡 Próximos Passos

* [ ] Realizar mais testes para ajustar o prompt do sistema (instruções do agente) para obter respostas ainda melhores.
* [ ] Adicionar os materiais do próximo bimestre.
* [ ] Implantar este agente como um aplicativo web (Web App) no Azure para que eu possa acessá-lo de qualquer dispositivo.
