O objetivo deste Repositório é criar um dashboard de vendas em Excel, transformando dados brutos em informações visuais claras e úteis para análise de desempenho e tomada de decisão.

## **O que fazer**
- **Descrição:**: Criar um dashboard de vendas no Excel que responda às perguntas de negócio listadas abaixo e entregue um arquivo Excel com o dashboard pronto.

## **Perguntas que o dashboard deve responder**
- **Total de vendas do plano anual**: soma das vendas relacionadas ao plano anual.
- **Total de vendas do plano anual — é auto-renovável?**: indicar se cada venda do plano anual é auto-renovável e agrupar os totais por tipo (renovável vs não renovável).
- **Total de vendas do EA Play**: soma das vendas/assinaturas do EA Play.
- **Total de vendas do Minecraft Season Pass**: soma das vendas do Minecraft Season Pass.
- **Quantidade de jogadores por gênero**: total masculino, feminino e total geral (independente do gênero).
- **Total de jogadores por tipo de plano**: agrupar quantidade de jogadores por cada tipo de plano/assinatura.

## **Requisitos**
- **Arquivo entregue:**: arquivo Excel `.xlsx` com o dashboard e dados de exemplo.
- **Versão recomendada:**: Excel 2016+ ou Microsoft 365 para melhor compatibilidade.

## **Estrutura sugerida do Excel**
- **Aba `Assets`**: Lugar onde temos as cores padrão usadas e imagens.
- **Aba `Bases`**: tabela com os dados brutos (datas, ID do usuário, tipo de plano, valor, renovação automática, gênero, produto, etc.).
- **Aba `Cálculos`**: tabelas auxiliares e cálculos (KPIs e colunas calculadas).
- **Aba `Dashboard`**: gráficos, KPIs e visualizações finais.

## **Como abrir e usar (passos rápidos)**
- **1. Abrir o arquivo:**: clique duas vezes no arquivo `.xlsx` para abrir no Excel.
- **2. Habilitar conteúdo:**: se aparecer aviso de segurança, clique em `Habilitar Conteúdo` para permitir macros e conexões.

## **Boas práticas e recomendações**
- **Formatação de colunas**: garanta que colunas de data e numéricas estejam no formato correto para evitar erros em cálculos e gráficos.
- **Nomes de intervalo**: use nomes de intervalo ou tabelas do Excel (`Ctrl+T`) para facilitar referências em fórmulas.

## **Entregáveis esperados**
- **`Arquivo_final.xlsx`**: planilha com o dashboard final.
- **`README.md`**: este arquivo com instruções e explicações.
- **`imagens/`**: capturas de tela demonstrando o dashboard e insights.

![imagem](imagens/imagem.png)

## **Construção Do Dashboard**

	- Tabela Dinâmica 1: filtro por **tipo de mensalidade**, **tipo de plano**, **sexo** com o total de reais recebidos por atualização automatica do serviço.
    - Tabela Dinâmica 2: filtro por **tipo de mensalidade**, **tipo de plano**, **sexo** com o total IDs por assinantes do serviço EA Play Season Pass com valor sim.
    - Tabela Dinâmica 2: filtro por **tipo de mensalidade**, **tipo de plano**, **sexo** com o total IDs por assinantes do serviço Minecraft Season Pass com valor sim.

	- Para preencher a coluna `Sexo` foi necessário extrair o prenome a partir da coluna `Nome` e mapear para `Masculino` ou `Feminino` usando uma tabela de referência de prenomes (ou regra/lookup definida no projeto).
	- Exemplo de abordagem utilizada (extrair primeiro nome + PROCV em uma tabela de prenomes):

		`=SEERRO(PROCV(ESQUERDA(A2;PROCURAR(" ";A2)-1); Prenomes!$A:$B; 2; FALSO); 0)`

- **Tratamento de erros (`#REF!` e outros):**
	- Em várias fórmulas onde havia risco de erro (referências inválidas ou buscas sem correspondência), usamos `SEERRO()` para capturar qualquer erro e retornar um valor padronizado (`0`) — facilitando os cálculos e a criação das Tabelas Dinâmicas.
- **Observações técnicas:**

## **Construção do Dashboard**
- **Visão geral:** O dashboard foi criado a partir de três Tabelas Dinâmicas principais, cada uma projetada para responder grupos específicos de perguntas e KPIs (receita, contagens por produto e segmentação demográfica).

- **Tabelas Dinâmicas e filtros usados:**
	- **Tabela Dinâmica — Receita por Mensalidade:** filtro por `Tipo de Mensalidade` (ex.: mensal, anual) e `Tipo de Plano` — usada para calcular o total de receita por categoria.
	- **Tabela Dinâmica — Contagem por Plano/Produto:** filtro por `Tipo de Plano` (ex.: EA Play, Minecraft Season Pass, etc.) — usada para contar IDs/assinaturas por produto e comparação entre planos.
	- **Tabela Dinâmica — Segmentação Demográfica:** filtro por `Sexo` — usada para comparar distribuição de jogadores por gênero e cruzar com tipos de plano.

- **Extração do sexo a partir do nome:**
	- Abordagem: extrair o primeiro nome a partir da coluna `Nome` e fazer lookup em uma tabela de prenomes que contém o gênero associado.
	- Fórmula de exemplo (Excel em português) que trata casos sem espaço no nome e erros de busca:

		`=SEERRO(PROCV(ESQUERDA(A2;PROCURAR(" ";A2&" ")-1); Prenomes!$A:$B; 2; FALSO); "Indefinido")`

		- Explicação: `ESQUERDA(...;PROCURAR(" ";A2&" ")-1)` extrai o primeiro prenome mesmo quando não há espaço; `PROCV` busca o gênero na tabela `Prenomes`; `SEERRO` captura `#N/D`, `#REF!` e outros erros, retornando `"Indefinido"` (ou `0`, conforme preferência) para facilitar agregações.

- **Tratamento de erros (`#REF!`, `#N/D`, etc.):**
	- Sempre que uma fórmula pode gerar erro por ausência de correspondência ou referência inválida, usamos `SEERRO()` para retornar um valor padrão (`0` ou `"Indefinido"`) — isso evita que erros interrompam as Tabelas Dinâmicas e permite somas/contagens consistentes.

- **Observações técnicas e boas práticas:**
	- Converta os dados em **Tabelas do Excel** (`Ctrl+T`) para que referências estruturadas e Tabelas Dinâmicas atualizem automaticamente ao inserir novos registros.
	- Use **Intervalos Nomeados** para ranges estáticos (ex.: a tabela `Prenomes`) e fórmulas com referências estruturadas quando possível.
	- Para atualizar manualmente as Tabelas Dinâmicas: `Dados → Atualizar Tudo` ou clique com o botão direito na Tabela Dinâmica e escolha `Atualizar`.

## **Conclusão**
- **Resumo dos resultados:** A construção com três Tabelas Dinâmicas, combinada com a extração de sexo a partir do prenome e o tratamento robusto de erros via `SEERRO()`, permite responder às perguntas do desafio (totais por plano, renovação automática, vendas por produto e segmentação por gênero) de forma confiável e com fácil atualização dos dados.
- **Limitações e cuidados:** A classificação de gênero por prenome depende da qualidade e cobertura da tabela de `Prenomes` — nomes ambíguos, apelidos ou culturas diferentes podem gerar classificações incorretas; por isso retornamos `"Indefinido"` quando não houver correspondência.
- **Próximos passos sugeridos:**
	- Expandir a lista de prenomes e revisar manualmente casos `Indefinido`.
	- Adicionar validações/limpeza dos dados de entrada (remoção de duplicatas, normalização de nomes).
	- Automatizar a atualização das Tabelas Dinâmicas com uma macro simples (opcional, gerando um `.xlsm`).
	- Incluir uma seção de documentação das principais fórmulas e nomes de intervalo para facilitar manutenção.
	- Recomenda-se usar Intervalos Nomeados ou Converter os dados em Tabela do Excel (`Ctrl+T`) para que as Tabelas Dinâmicas atualizem corretamente ao inserir novos registros.
