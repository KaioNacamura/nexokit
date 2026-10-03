# Requisitos

## Funcionais

| Código | Requisito |
| --- | --- |
| RF01 | Cadastrar equipamentos com nome, patrimônio único e categoria. |
| RF02 | Editar e buscar equipamentos, mostrando se estão disponíveis, emprestados ou inativos. |
| RF03 | Ativar ou inativar equipamentos sem apagar o histórico. |
| RF04 | Cadastrar, editar e buscar alunos por nome, RA único e curso. |
| RF05 | Ativar ou inativar alunos sem apagar o histórico. |
| RF06 | Registrar empréstimos com equipamento, aluno, data da retirada, prazo e observação opcional. |
| RF07 | Registrar a devolução e liberar o equipamento para outro empréstimo. |
| RF08 | Consultar detalhes e filtrar o histórico por situação: em andamento, atrasado ou devolvido. |
| RF09 | Mostrar no painel equipamentos disponíveis, empréstimos abertos, atrasados e alunos ativos. |
| RF10 | Exportar para CSV os empréstimos encontrados na busca e no filtro. |
| RF11 | Oferecer modo de demonstração com dados fictícios separado dos dados de uso. |

## Não funcionais

| Código | Requisito |
| --- | --- |
| RNF01 | Interface em português, com campos identificados e mensagens fáceis de entender. |
| RNF02 | Funciona sem internet, em Python 3.10 ou mais novo com Tkinter; janela mínima de 1000 x 740 pixels. |
| RNF03 | Dados guardados em SQLite e mantidos depois de fechar e abrir o programa. |
| RNF04 | Sem duplicidade e sem empréstimo com aluno ou equipamento inválido. |
| RNF05 | Orientação a objetos, com interface, regras e acesso ao banco separados. |
| RNF06 | Consultas e gravações em até 2 segundos com 1.000 equipamentos, 500 alunos e 2.000 empréstimos. |
| RNF07 | Guardar só nome, RA e curso do aluno; consultas parametrizadas; CSV protegido contra fórmulas. |
| RNF08 | Cópia manual do banco, com o programa fechado, para recuperação. |

## Regras de negócio

- Um equipamento só pode ter um empréstimo aberto por vez.
- Aluno ou equipamento com empréstimo aberto não pode ser inativado.
- O prazo não pode ser antes da retirada.
- O empréstimo fica atrasado a partir do dia seguinte ao prazo.
- A devolução só pode ser registrada uma vez.

## Fora do escopo

Login, aplicativo de celular, acesso pela internet, vários atendentes ao mesmo tempo, reservas, multas, pagamentos, envio de mensagens e integração com os sistemas da faculdade.
