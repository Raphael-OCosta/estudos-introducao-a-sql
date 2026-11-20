# 🗃️ Estudos — *Introdução à Linguagem SQL* (Thomas Nield) · ✅ concluído

> **A melhor forma de estudar um livro técnico é ler e praticar ao mesmo tempo.**
> Leia um trecho e, em seguida, escreva e rode as consultas você mesmo, no seu banco.

Este repositório registra como estudei *Introdução à Linguagem SQL* (O'Reilly): lendo cada capítulo e escrevendo as consultas no **VS Code**, com o **DBeaver** como gerenciador visual dos bancos SQLite do livro.

## 🔁 O método

1. **Ler** o capítulo no PDF (o guia indica a página e o banco de cada capítulo).
2. **Praticar**: digitar as consultas num arquivo `.sql` do capítulo e rodar com `Ctrl+Enter`.
3. **Variar**: mudar filtros, colunas e agrupamentos para ver o que acontece.
4. **Conferir no DBeaver**: olhar as tabelas e os resultados de forma visual.
5. **Registrar**: anotar o que aprendeu e fazer commit.

## 🛠️ Melhorias em relação ao livro

- O livro usa o SQLiteStudio. Aqui o ambiente é **VS Code + SQLTools** (conexões prontas para os 5 bancos do livro), com `Ctrl+Enter` executando a consulta sob o cursor e os resultados reaproveitando a mesma aba.
- **DBeaver** configurado com os mesmos bancos, para explorar as tabelas visualmente.
- [Guia de Estudos (PDF)](estudos/Guia_de_Estudos_SQL.pdf) para iniciantes: glossário, primeira vez clique a clique, rotina de 60 minutos, mapa capítulo → página → banco e erros comuns. Também está em [Markdown](estudos/COMO_ESTUDAR.md).

## 📁 O que está aqui (e o que não está)

| Está aqui | Fica só na minha máquina |
|---|---|
| guia em PDF/HTML/Markdown, configuração do VS Code | bancos `.db` e materiais do repositório do autor |
| | meus arquivos `.sql` de prática (têm as consultas transcritas do livro) |

Os bancos e o material oficial estão em [thomasnield/oreilly_getting_started_with_sql](https://github.com/thomasnield/oreilly_getting_started_with_sql). Para estudar, clone o repositório do autor e copie para dentro dele a pasta `estudos/` e a `.vscode/` daqui.

## ⚖️ Direitos autorais

O livro e os bancos do autor **não** estão neste repositório. Para estudar, use a sua própria cópia.
O guia e as configurações são autorais e estão sob licença [MIT](LICENSE).
