# Desafio Técnico Inovação - ViaCerta BANKING

Este documento descreve o desafio técnico para a vaga de Desenvolvedor de Software da ViaCerta BANKING.

## Considerações sobre o desafio

* O prazo para entrega da solução é de 7 dias corridos, contados a partir da data de recebimento do desafio. Caso você precise de mais tempo, entre em contato com o resposável pelo seu processo seletivo e fechamos uma nova data para a entrega. Não se preocupe, o importante é a qualidade da solução entregue
* O desafio consiste em construir uma API .Net
* Utilize a linguagem C# e o .NET mais recente disponível
* A utilização de frameworks/bibliotecas é livre para a construção da solução, procuramos uma solução simples evite poluir demais o código com muitos frameworks desnecessários
* Em relação aos dados, estes poderão ser armazenados em banco de dados relacional à sua escolha
* O código produzido deve estar versionado em algum repositório público (Github, Bitbucket etc.)
* Quando estiver tudo pronto, você deve mandar um e-mail com o link do seu repositório para o responsável pelo seu processo seletivo
* A solução deve conter alguns testes unitários (não precisa de 100% de cobertura)

## Desafio

Uma financeira deseja um sistema que irá avaliar o crédito dos seus clientes de acordo com os dados de cadastro.

Para isso foi solicitado que você desenvolva uma API que irá receber em um método os dados do cliente e efetuar um cadastro. Deverá ser possível cadastrar, consultar pelo CPF e excluir pelo CPF
Dados do cliente:
* CPF (Válido)
* Data Nascimento
* Salário
* Endereço
* * Estado
* * Cidade

Também devemos ter um método que irá receber o CPF do cliente e efetuar uma avaliação de crédito para ele.

Resultado da avaliação de crédito:
* Situação (Aprovado, Reprovado)
* Limite

Para avaliar o crédito do cliente existem algumas regras, no caso do não cumprimento o cliente deverá ser Reprovado;
* O cliente deve ter 18 anos ou mais completados na data de envio dos dados.
* O cliente não pode residir na cidade "Santo Cristo" do estado "RS".

Para definir o limite do cliente deverá ser considerada a seguinte tabela:
   
    | Salário do cliente | Multiplicador |
    |:-------------------|--------------:|
    |até 1.000,00|30%|
    |de 1.000,01 até 5.000,00|40%|
    |de 5.000,01 até 10.000,00|60%|
    |de 10.000,01 até 20.000,00|70%|
    |acima de 20.000,01|80%|

Onde o Multiplicador deve ser usado em cima do salário para encontrar o limite. Ex: Salário de R$ 1050,00, limite de R$ 420 (40% de 1050)
   
Além disso o sistema deverá respeitar a seguinte tabela de teto de limite:
    
    | Idade do cliente | Valor máximo de limite |
    |:-----------------------|--------------:|
    |até 25 anos|R$ 7.000|
    |de 26 até 30|R$ 12.500|
    |de 30 até 65|R$ 60.000|
    |acima 65|R$ 20.000|

## Documentação e Deploy

Crie uma documentação (Pode ser Readme.md) breve sobre a sua solução, com explicação sobre a arquitetura/design, hipóteses assumidas, frameworks utilizados e por quê.

Esperamos também um passo a passo de como executar a sua solução. Quanto mais simples, melhor. Vale ressaltar que a execução **não poderá depender do uso de alguma IDE específica**.

## Bônus

* Frontend de utilização da API. (Recomendamos Swagger)
* Conteinerização do projeto com Docker.
* Publicação da aplicação funcional em algum serviço.

## Avaliação

A sua solução será avaliada por líderes técnicos aqui da ViaCerta, com base nos seguintes critérios:

* **Compilação e Testes:** A solução está compilando e executando testes com sucesso?
* **Regras de negócio:** A solução está atendendo todas regras de negócio especificadas?
* **Qualidade de código:** O código escrito é de fácil leitura? O quão complexo seria extender esse código com novas funcionalidades? A arquitetura está organizada?
