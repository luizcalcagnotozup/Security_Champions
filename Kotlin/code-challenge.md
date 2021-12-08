# Code_Challenge - Kotlin

**Olá Zupper!**

Neste pequeno desafio, vamos propor um cenário e um problema e gostariamos que você descrevesse com suas palavras como resolver esse problema.

## Cenário
Em uma determinada Imobiliária existe um sistema com back-end em Kotlin/Micronaut para controle dos imóveis disponíveis.
Para aumentar o engajamento dos corretores, uma bonificação é paga mensalmente para aqueles que conseguirem cadastrar mais imóveis na plataforma.

O sistema possuí login por meio de autenticação com JWT. Existem três possíveis usuários da plataforma: Usuários (clientes), Corretores e Administrador

## Problema
Por algum motivo, um determinado corretor de uma hora pra outra, começou a ganhar todos os meses a bonificação. Um colega seu, confiante de que deveria conseguir
a bonificação em determinado mês, resolveu checar a quantidade de imóveis cadastrados que ele havia cadastrado e percebeu que um dos que havia cadastrado já não
existia na plataforma. Com isso resolveu falar com o Gerente, que então entrou em contato com a empresa que desenvolveu a plataforma.

## Resolução
Baseado no código abaixo, formule uma explicação do que pode ter ocorrido.

O Controller da API no arquivo challenge.kt

## Solução
Os endpoints de cadastrar e remover possuem somente duas ROLES que seriam "ROLE_ADMIN e ROLE_CORRETOR", com esse permissionamento, qualquer um pode adicionar ou excluir um imóvel, no caso, um corretor "X", pode tranquilamente excluir um imóvel do corretor "Y", e depois cadastrar este imóvel no nome do corretor "X".

Para solucionar este problema, poderiamos utilizar o "Micronauts Validation", para validar se o ID do imóvel cadastado, esta vinculado ao corretor que solicitou a remoção, caso esteja vinculado ele deixar remover o imóvel. Desta forma somente quem cadastrou o imóvel consegue exclui-lo. Seria interessante também adicionar o OAuth 2 para ter o histórico de acessos aos endpoints e passar todo o permissionamento para ele.
