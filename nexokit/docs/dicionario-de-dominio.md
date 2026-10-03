# Dicionário de domínio

Tipos conceituais: Texto, Data e Booleano. Atributos com barra (`/situacao`) são calculados pelo sistema.

## Aluno

Quem vai ao balcão pegar ou devolver o equipamento. Não usa o sistema.

- **Responsabilidade:** identificar quem está com cada equipamento e dizer se o aluno pode fazer novos empréstimos.
- **Relacionamentos:** faz 0..* empréstimos.

| Atributo | Tipo | Significado |
| --- | --- | --- |
| nome | Texto | Nome completo |
| ra | Texto {único} | Registro acadêmico |
| curso | Texto | Curso do aluno |
| ativo | Booleano | Falso quando não pode mais pegar equipamentos |

## Equipamento

Item físico da central que pode ser emprestado.

- **Responsabilidade:** guardar os dados do item e informar se ele está disponível, emprestado ou inativo.
- **Relacionamentos:** pertence a 1 categoria e aparece em 0..* empréstimos.

| Atributo | Tipo | Significado |
| --- | --- | --- |
| nome | Texto | Como o item é chamado no balcão |
| patrimonio | Texto {único} | Número da etiqueta de patrimônio |
| ativo | Booleano | Falso quando o item quebra ou é descartado |
| /situacao | SituacaoEquipamento | DISPONIVEL, EMPRESTADO ou INATIVO |

## Categoria

Tipo de equipamento (Projetor, Microfone, Adaptador).

- **Responsabilidade:** agrupar os equipamentos do mesmo tipo para a busca e o filtro.
- **Relacionamentos:** classifica 0..* equipamentos.

## Emprestimo

Cada vez que um aluno leva um equipamento.

- **Responsabilidade:** registrar a retirada e a devolução e informar se está em andamento, atrasado ou devolvido.
- **Relacionamentos:** tem 1 aluno e 1 equipamento.

| Atributo | Tipo | Significado |
| --- | --- | --- |
| dataRetirada | Data | Dia em que o aluno levou |
| dataPrevista | Data | Prazo para devolver |
| dataDevolucao | Data [0..1] | Vazia enquanto o empréstimo está aberto |
| observacao | Texto [0..1] | Anotação do atendente |
| /situacao | SituacaoEmprestimo | EM_ANDAMENTO, ATRASADO ou DEVOLVIDO |
