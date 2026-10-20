# Folha de Pagamento

Autor: Gabriel Mancio.

Projeto do trabalho de Gestão e Qualidade de Software. O sistema tem como objetivo organizar os dados dos colaboradores e automatizar o cálculo dos salários por categoria, permitindo conferir os valores individuais e o custo total da folha.

## Situação atual

Documentação revisada e organização inicial do repositório. A implementação está pendente. As funcionalidades, tecnologias e verificações descritas nos documentos são planejadas; ainda não há aplicação, banco de dados ou testes automatizados implementados.

## Funcionalidades previstas

- Cadastro, consulta, alteração e exclusão de colaboradores, com matrícula única.
- Cálculo de salários para colaboradores padrão, comissionados e por produção.
- Folha individual e consolidada com matrícula, nome, tipo, salário base, adicionais e salário final.
- Resumo com total geral e, conforme a extensão recomendada adotada no projeto, quantidade de colaboradores e totais por categoria.
- Validação dos dados antes de salvar ou calcular e armazenamento persistente dos cadastros.

## Categorias e cálculos previstos

| Categoria | Salário final |
| --- | --- |
| Colaborador padrão | Salário base. |
| Colaborador comissionado | Salário base + comissão sobre as vendas. Comissão = vendas × (percentual informado / 100). |
| Colaborador por produção | Salário base + quantidade produzida × valor por unidade. |

Todos os tipos recebem salário base. No campo de comissão, 5 representa 5%, equivalente ao fator 0,05. Conforme a ERS, o salário final individual será arredondado pela regra de metade para cima e apresentado com duas casas decimais; o total será a soma desses salários.

## Tecnologias e arquitetura planejadas

| Parte | Tecnologia planejada |
| --- | --- |
| Interface | React, Vite e TypeScript. |
| Servidor | Node.js, Express e TypeScript. |
| Comunicação | API REST com JSON. |
| Banco de dados | SQLite, com consultas SQL parametrizadas. |
| Testes automatizados | Vitest. |

A arquitetura será dividida em camadas: interface, controladores e validação, domínio com as regras de remuneração e repositório para acesso ao banco. Os cálculos ficarão separados das telas e das consultas SQL.

A interface enviará solicitações HTTP à API REST e receberá dados ou mensagens de erro em JSON. GET será usado para consultas, POST para cadastro, PUT para alteração e DELETE para exclusão. A API validará os dados, acionará as regras de negócio e acessará o SQLite por meio do repositório.

## Organização das pastas

| Pasta | Finalidade |
| --- | --- |
| `01_Requisitos` | Visão do sistema, requisitos e rastreabilidade. |
| `02_Analise` | Modelagem UML e descrição dos casos de uso. |
| `03_Projeto` | Arquitetura e planejamento do projeto. |
| `04_Testes` | Plano de testes e especificação dos casos de teste. |
| `05_Codigo_Fonte` | Reservada para a implementação futura. |
| `06_Banco_Dados` | Reservada para futuros scripts e estrutura do banco. |
| `07_Executavel` | Reservada para a futura entrega executável. |
| `08_Manuais` | Reservada para os futuros manuais. |
| `09_Homologacao` | Reservada para os futuros registros de homologação. |
| `10_Qualidade` | Plano de garantia da qualidade. |
| `11_Apresentacao` | Reservada para a apresentação futura do trabalho. |

As pastas reservadas contêm somente `.gitkeep` para serem registradas pelo Git.

## Documentos revisados

- [Documento de Visão](01_Requisitos/01_Documento_de_Visao.docx).
- [ERS e Rastreabilidade](01_Requisitos/02_ERS_e_Rastreabilidade.docx).
- [Modelagem UML](02_Analise/03_Modelagem_UML.docx).
- [Arquitetura](03_Projeto/04_Arquitetura.docx).
- [Planejamento do Projeto](03_Projeto/08_Planejamento.docx).
- [Plano de Testes](04_Testes/06_Plano_Testes.docx).
- [Casos de Teste](04_Testes/07_Casos_Testes.docx).
- [Plano de Garantia da Qualidade](10_Qualidade/05_Plano_Qualidade.docx).

Os documentos Word foram preservados sem alterações. O ZIP original permanece como cópia local, fora do versionamento.
