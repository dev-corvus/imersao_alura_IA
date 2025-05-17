Imersão IA 3ª Edição - Alura e Google Gemini
============================================

Visão Geral do Projeto
----------------------

Este projeto foi desenvolvido como parte da Imersão em Inteligência Artificial, 3ª Edição, uma iniciativa da Alura em parceria com o Google. O objetivo principal é criar um aplicativo web que permita aos usuários rastrear suas informações de macro nutrientes (proteínas, carboidratos, gorduras, fibras e açúcares) a partir dos alimentos que consomem. O aplicativo utiliza o modelo Gemini do Google para estimar os valores nutricionais a partir de descrições textuais dos alimentos.

Funcionalidades
---------------

O aplicativo oferece as seguintes funcionalidades:

-   Registro de Alimentos: Os usuários podem inserir a descrição de um alimento consumido utilizando uma linguagem natural.

-   Estimativa de Macronutrientes: O aplicativo utiliza o modelo Gemini do Google para estimar os valores nutricionais do alimento inserido. Para este projeto foi considerado as macros: proteína, carboidratos, gordura, fibra e açúcar.

-   Armazenamento de Dados: Os dados dos alimentos e seus respectivos macros são armazenados para gerar um resumo diário.

-   Interface Web: O usuário interage com o sistema através de uma interface web de fácil uso.

Tecnologias Utilizadas
----------------------

O projeto foi construído utilizando as seguintes tecnologias:

-   Frontend:

    -   HTML

    -   CSS

    -   JavaScript

-   Backend:

    -   Python

    -   Flask

-   Modelo de IA:

    -   Google Gemini (gemini-2.0-flash)

-   Outros:

    -   Google Colab

    -   Ngrok

Como Executar o Projeto
-----------------------

Siga estas etapas para executar o projeto em seu ambiente:

1.  Configurar o Google Colab:

    -   Abra um novo notebook no Google Colab.

    -   Certifique-se de ter uma chave de API do Google e armazene-a em Colab Secrets com o nome `GOOGLE_API_KEY`.

2.  Executar o Código:

    -   Cole o código fornecido (que inclui o código Flask, a integração com Gemini e o HTML) em uma célula do Colab.

    -   Execute a célula. O Colab irá instalar as dependências necessárias, iniciar o servidor Flask e configurar o Ngrok para fornecer um URL público.

3.  Acessar o Aplicativo:

    -   O Ngrok irá gerar um URL público. Abra este URL em seu navegador web.

    -   Você verá a interface do aplicativo, onde poderá inserir os alimentos e registrar as refeições.

Estrutura do Código
-------------------

O código do projeto está estruturado da seguinte forma:

-   Código Python (Flask):

    -   Define o aplicativo Flask.

    -   Cria as rotas `/` (para servir o HTML) e `/log_meal` (para receber os dados da refeição).

    -   Integra-se com o modelo Gemini para estimar os macros.

    -   Armazena os dados das refeições em uma lista.

    -   Retorna os dados para o frontend.

-   Código HTML (index.html):

    -   Define a estrutura da página web, incluindo os campos de entrada para descrição do alimento e tipo de refeição, e o botão para registrar a refeição.

    -   Inclui o código JavaScript para interagir com o servidor Flask.

-   Código JavaScript:

    -   Captura os eventos do usuário (clique no botão "Log Meal").

    -   Envia os dados da refeição para o servidor Flask usando `fetch`.

    -   Recebe a resposta do servidor e atualiza a página com o resumo diário.

-   Funções Principais:

    -   `get_macro_estimate(food_description)`: Envia um prompt para o Gemini para estimar os macros de um alimento.

    -   `extract_macros(text)`: Extrai os valores dos macros da resposta do Gemini.

    -   `log_meal_route()`: Rota do Flask para registrar uma refeição.

    -   `display_summary(daily_macros)`: Exibe o resumo diário dos macros.

Próximos Passos
---------------

Este projeto pode ser expandido e aprimorado com as seguintes funcionalidades:

-   Persistência de Dados: Utilizar um banco de dados (como SQLite ou PostgreSQL) para armazenar os dados das refeições de forma persistente, em vez de usar uma lista temporária.

-   Interface de Usuário Mais Rica: Melhorar a interface do usuário com um framework CSS (como Bootstrap ou Tailwind) e adicionar mais interatividade.

-   Validação de Dados: Adicionar mais validação de dados no frontend e no backend para garantir que os usuários insiram informações corretas.

-   Cálculo de Necessidades Calóricas: Permitir que os usuários insiram seus dados pessoais (idade, sexo, altura, peso, nível de atividade) e calcular suas necessidades calóricas diárias e definir metas de macronutrientes desejados.

-   Integração com Outras APIs: Integrar com outras APIs de nutrição para obter dados mais precisos sobre os alimentos e sugerir um plano alimentar.

-   Funcionalidades de Compartilhamento: Permitir que os usuários compartilhem seus resumos diários em redes sociais.

Conclusão
---------

Este projeto demonstra uma aplicação prática do modelo Gemini do Google para resolver um problema do mundo real: o rastreamento de informações nutricionais. Ele também ilustra como construir um aplicativo web completo usando Python, Flask, HTML, CSS e JavaScript. Este projeto foi desenvolvido como parte da Imersão IA da Alura, e representa um ponto de partida para aplicações mais complexas na área de saúde e bem-estar.
