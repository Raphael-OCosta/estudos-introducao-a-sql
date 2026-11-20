# Como estudar — Introdução à Linguagem SQL (Thomas Nield)

> 📄 **Versão para ler:** `Guia_de_Estudos_SQL.pdf` (nesta pasta). Fonte do PDF: `guia_pdf/guia.html`.

Este guia é para quem está começando do zero. Siga na ordem: **Parte 1** uma única vez, **Parte 2** todo dia.

---

## O que é cada coisa (em uma frase)

| Coisa | Para que serve | Comparação |
|---|---|---|
| **O livro (PDF)** | Explica o assunto e mostra as consultas | O professor |
| **Arquivos `.db`** (na pasta do repositório) | São os bancos de dados com as tabelas do livro | O "Excel" com os dados |
| **SQL** | A linguagem que você escreve para perguntar coisas ao banco | As fórmulas |
| **VS Code + SQLTools** | Onde você **escreve e roda** suas consultas e guarda suas anotações | Seu caderno |
| **DBeaver** | Onde você **olha** as tabelas, colunas e dados com o mouse | O "explorador de arquivos" do banco |

> O livro usa um programa chamado **SQLiteStudio**. Você **não** precisa dele: o VS Code e o DBeaver fazem a mesma coisa.
> Sempre que o livro falar em SQLiteStudio, use a tabela de "tradução" no fim deste guia.

Onde fica cada coisa no computador:

- Pasta do curso: `C:\estudos\oreilly_getting_started_with_sql`
- Seus arquivos de exercício: `C:\estudos\oreilly_getting_started_with_sql\estudos\` (um `.sql` por capítulo)
- Livro: `C:\Users\rrcosta\OneDrive\Livros\Ebooks Data Science\O'Reilly - PT - Introdução à Linguagem SQL - Thomas Nield.pdf`

---

## Parte 1 — Primeira vez (uns 15 minutos, só uma vez)

### 1.1 Abrir a pasta no VS Code

1. Abra o **VS Code**.
2. Menu **File → Open Folder…** (ou *Arquivo → Abrir Pasta…*).
3. Escolha `C:\estudos\oreilly_getting_started_with_sql` e clique em **Selecionar pasta**.
4. Se aparecer "Do you trust the authors of the files in this folder?", clique em **Yes, I trust the authors**.
5. No painel da esquerda (**Explorer**, o ícone de duas folhas) você verá os arquivos `.db` e a pasta `estudos`.

### 1.2 Conectar o VS Code a um banco (SQLTools)

1. Na barra vertical da esquerda, clique no ícone de **cilindro** (banco de dados) chamado **SQLTools**.
   Se não achar, aperte `Ctrl+Shift+P`, digite `SQLTools: Focus on Connections` e Enter.
2. Em **CONNECTIONS** aparecem 4 conexões: `rexon_metals`, `weather_stations`, `surgetech_conference`, `extra_practice (Chinook)`.
3. Passe o mouse sobre **rexon_metals** e clique no ícone de **tomada (Connect)** que aparece à direita.
4. **Só na primeira vez:** aparece um aviso no canto inferior direito pedindo para instalar o `sqlite3`
   ("SQLite driver requires node sqlite3…"). Clique em **Install now** e espere terminar (1–2 min).
   Depois clique na tomada de novo.
5. Conectou quando aparece um **ponto verde** ao lado do nome e dá para expandir a seta e ver **Tables → CUSTOMER, PRODUCT, CUSTOMER_ORDER**.

### 1.3 Rodar a primeira consulta no VS Code

1. Volte ao **Explorer** (ícone de folhas), abra `estudos → cap04_select.sql`.
2. Você verá a linha `SELECT * FROM CUSTOMER;`.
3. Logo **acima** dessa linha aparece um texto pequeno e clicável: **Run on active connection**. Clique nele.
   - Alternativa: selecione a linha com o mouse e aperte `Ctrl+E` e depois `Ctrl+E` de novo.
4. Abre uma aba à direita com uma tabela de **5 clientes**. Pronto — você rodou SQL. 🎉
5. Confira na **barra azul inferior** do VS Code qual conexão está ativa (ex.: `rexon_metals`).
   **Importante:** a consulta sempre roda na conexão ativa. Se mudar de capítulo/banco, conecte no banco certo antes.

### 1.4 Abrir o mesmo banco no DBeaver

1. Abra o **DBeaver** (menu Iniciar → DBeaver).
2. Se perguntar sobre "Create sample database", clique **No**. Se pedir para escolher tema/estatísticas, pode fechar.
3. No painel esquerdo **Database Navigator**, abra a pasta **Livro SQL** → você verá as mesmas 4 conexões.
4. Dê **duplo clique em `rexon_metals`**.
5. **Só na primeira vez:** abre a janela "Driver settings / Download driver files". Clique **Download** e espere.
6. Expanda: `rexon_metals → Tables → CUSTOMER`. Dê duplo clique em **CUSTOMER**. Abre uma janela com abas:
   - **Properties**: as colunas e o tipo de cada uma (INTEGER, TEXT…). É o que o livro chama de *Structure*.
   - **Data**: os dados da tabela. É o que o livro chama de *Data*.
   - **ER Diagram**: o desenho das tabelas e de como se ligam (vai ajudar no capítulo 8 e 9).
7. Para escrever SQL no DBeaver: clique com o botão direito em `rexon_metals` → **SQL Editor → Open SQL script**
   (atalho `Ctrl+]`). Escreva `SELECT * FROM CUSTOMER;` e aperte `Ctrl+Enter`. O resultado aparece embaixo.

> **Qual usar?** Escreva os exercícios no **VS Code** (fica tudo salvo nos arquivos `capXX`).
> Use o **DBeaver** para *explorar*: ver colunas, dados e diagramas quando não lembrar o nome de algo.

---

## Parte 2 — Rotina de cada sessão de estudo (60 min)

| Tempo | O que fazer |
|---|---|
| 5 min | Abra o PDF na página do capítulo (tabela abaixo). Abra o VS Code na pasta e o arquivo `capXX` do dia. Conecte no banco do capítulo. |
| 15 min | **Leia** um pedaço do capítulo (uma seção, ex.: "Expressões em instruções SELECT"). |
| 25 min | **Digite** cada consulta que aparece no livro no seu arquivo `capXX` — digitar, não copiar/colar. Rode cada uma e compare o resultado com a figura do livro. Depois **mude algo** (outra coluna, outro número) e veja o que acontece. |
| 10 min | Escreva **1 ou 2 consultas suas** sobre o mesmo assunto (ex.: "quais produtos custam mais de 10?"). |
| 5 min | Escreva em comentário (`-- ...`) no arquivo o que aprendeu e dúvidas. Salve (`Ctrl+S`). |

Ritmo sugerido: **1 capítulo a cada 2–3 sessões**. O livro inteiro sai em ~4 semanas.

### Mapa: capítulo → página do PDF → banco → arquivo

| Capítulo | Página no PDF | Conecte em | Arquivo |
|---|---|---|---|
| 1 · Por que aprender SQL? | 14 | — (só leitura) | — |
| 2 · Bancos de dados | 16 | — (só leitura) | — |
| 3 · SQLite | 22 | `rexon_metals` (no **DBeaver**, explore as tabelas como o livro faz) | — |
| 4 · SELECT | 30 | `rexon_metals` | `cap04_select.sql` |
| 5 · WHERE | 40 | `weather_stations` | `cap05_where.sql` |
| 6 · GROUP BY e ORDER BY | 51 | `weather_stations` | `cap06_group_by_order_by.sql` |
| 7 · CASE | 61 | `weather_stations` | `cap07_case.sql` |
| 8 · JOIN | 68 | `rexon_metals` | `cap08_join.sql` |
| 9 · Design de banco de dados | 83 | `surgetech_conference` | `cap09_design.sql` |
| 10 · Gerenciando dados | 109 | `surgetech_conference` | `cap10_gerenciando_dados.sql` |
| 11 · Seguindo em frente | 116 | — | — |
| Apêndice A · Operadores e funções | 120 | qualquer | `apendice_funcoes.sql` |
| Apêndice B · Índices e transações | 129 | qualquer | `apendice_funcoes.sql` |
| Prática extra (depois do livro) | — | `extra_practice (Chinook)` | `extra_chinook.sql` |

> "Página no PDF" é o número que o leitor de PDF mostra (não o número impresso na folha).

---

## Exemplo completo: primeira sessão do Capítulo 4

1. PDF na página **30**. VS Code com `cap04_select.sql` aberto. SQLTools conectado em **rexon_metals**.
2. O livro pede `SELECT * FROM CUSTOMER;` → já está no arquivo. Clique em **Run on active connection**. Resultado: 5 clientes.
3. Página 33: o livro mostra só duas colunas. Digite embaixo, numa linha nova:

   ```sql
   SELECT CUSTOMER_ID, NAME FROM CUSTOMER;
   ```

   Rode. Agora só aparecem 2 colunas.
4. Página 34: digite e rode

   ```sql
   SELECT
     PRODUCT_ID,
     DESCRIPTION,
     PRICE,
     PRICE * 1.07 AS TAXED_PRICE
   FROM PRODUCT;
   ```

   Experimente trocar `1.07` por `1.10` e rode de novo.
5. Sua consulta própria: "mostrar a descrição e o preço com desconto de 5%" → tente escrever sozinho.
6. Anote no fim do arquivo:

   ```sql
   -- Aprendi: SELECT escolhe colunas; * = todas; AS dá nome a uma coluna calculada.
   -- Dúvida: ...
   ```

**Regra de ouro no arquivo:** cada consulta termina com `;` e fica separada das outras por uma linha em branco.
Assim o "Run on active connection" aparece em cima de cada uma e você roda uma de cada vez.

---

## Tradução: o que o livro diz (SQLiteStudio) → o que você faz

| O livro diz… | No VS Code (SQLTools) | No DBeaver |
|---|---|---|
| "Database → Add a database" / abrir o `.db` | Já está pronto: clique na tomada da conexão | Já está pronto: duplo clique na conexão em *Livro SQL* |
| "Tools → Open SQL Editor" | Abra o arquivo `capXX.sql` | Botão direito na conexão → SQL Editor → Open SQL script (`Ctrl+]`) |
| "Clique no triângulo azul ou F9" | **Run on active connection** ou selecionar + `Ctrl+E Ctrl+E` | `Ctrl+Enter` (consulta onde está o cursor) · `Alt+X` (todas) |
| Painel "Query Results" | Aba de resultados que abre à direita | Painel de resultados embaixo do editor |
| Guia "Structure" | Expandir a tabela no SQLTools (mostra colunas) | Aba **Properties** da tabela |
| Guia "Data" | `SELECT * FROM TABELA;` ou clicar no `.db` no Explorer (SQLite Viewer) | Aba **Data** da tabela |
| Criar banco novo (cap. 9) | Não precisa: use `surgetech_conference` | Idem |

---

## Quando algo der errado

| Problema | Solução |
|---|---|
| Não aparece o ícone de cilindro do SQLTools na barra da esquerda | 1º veja o canto inferior esquerdo: se estiver escrito **Restricted Mode**, clique nele → **Trust** (confiar na pasta). Em modo restrito o VS Code desliga o SQLTools. Senão: `Ctrl+Shift+P` → digite `Reload Window` → Enter (recarrega o VS Code). Se ainda não aparecer: clique com o botão direito na barra de ícones da esquerda e marque **SQLTools**. Ou: menu **View → Open View…** → digite `SQLTools` → **Connections**. |
| `no such table: CUSTOMER` | Você está conectado no banco errado. Veja a barra azul inferior e conecte no banco da tabela do capítulo. |
| Não aparece "Run on active connection" | Nenhuma conexão ativa. Vá no ícone SQLTools e clique na tomada do banco. |
| Erro de sintaxe (`syntax error near…`) | Confira vírgulas entre colunas, `;` no final e aspas simples em textos: `'Texto'`. |
| Estraguei o banco nos capítulos 9–10 | Desconecte no SQLTools e no DBeaver. No terminal do VS Code (`Ctrl+'`), rode `git restore surgetech_conference.db`. |
| Chave externa não bloqueia nada (cap. 9–10) | Rode `PRAGMA foreign_keys = ON;` antes, na mesma conexão. |
| `5/2` deu `2` | No SQLite número inteiro dividido por inteiro dá inteiro. Use `5/2.0`. |
| DBeaver diz que o arquivo está bloqueado | Feche a conexão no VS Code (ou vice-versa) quando for alterar dados. |
