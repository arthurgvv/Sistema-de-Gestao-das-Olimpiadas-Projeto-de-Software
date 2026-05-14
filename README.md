# 🏅 Sistema de Gestão das Olimpíadas (SGO) 👨‍💻

> [!NOTE]
> Sistema desenvolvido para coordenar os diferentes aspectos das Olimpíadas, permitindo o gerenciamento de competições, inscrições de atletas, alocação de locais para as provas e controle de resultados.

<table>
  <tr>
    <td width="800px">
      <div align="justify">
        O <b>SGO (Sistema de Gestão das Olimpíadas)</b> é um projeto acadêmico desenvolvido para a disciplina de <i>Projeto de Software</i>, com foco exclusivo em <b>modelagem e diagramação UML</b>. O sistema foi projetado para coordenar todos os aspectos de um evento olímpico: cadastro de competições, inscrição de atletas, alocação de locais e controle de resultados com geração de quadro de medalhas. A modelagem segue uma arquitetura em camadas com padrão Facade, separando responsabilidades entre Apresentação, Negócio e Dados.
      </div>
    </td>
    <td>
      <div align="center">
        🏆
      </div>
    </td>
  </tr>
</table>

---

## 🚧 Status do Projeto

[![Versão](https://img.shields.io/badge/Versão-v1.0.0-blue?style=for-the-badge)](https://github.com/arthurgvv/Sistema-de-Gestao-das-Olimpiadas-Projeto-de-Software)
![PlantUML](https://img.shields.io/badge/PlantUML-Diagramação-007ec6?style=for-the-badge&logo=uml&logoColor=white)
![UML](https://img.shields.io/badge/UML-Modelagem-007ec6?style=for-the-badge)

---

## 📚 Índice
- [Sobre o Projeto](#-sobre-o-projeto)
- [Funcionalidades Principais](#-funcionalidades-principais)
- [Tecnologias Utilizadas](#-tecnologias-utilizadas)
- [Histórias de Usuário](#-histórias-de-usuário)
- [Arquitetura e Diagramas](#-arquitetura-e-diagramas)
- [Estrutura de Pastas](#-estrutura-de-pastas)
- [Documentações Utilizadas](#-documentações-utilizadas)
- [Autores](#-autores)

---

## 📝 Sobre o Projeto

O SGO foi desenvolvido como resposta à necessidade de coordenar os complexos processos logísticos e operacionais de um evento olímpico. O sistema centraliza o controle de competições, garante que atletas sejam inscritos respeitando as regras de representação por país, evita conflitos na alocação de locais e mantém um registro confiável de resultados e medalhas.

O projeto é composto exclusivamente por **modelagem UML**, sem implementação de código, abrangendo cinco diagramas complementares que representam diferentes perspectivas do sistema:

- **Casos de Uso:** interações entre atores e funcionalidades
- **Classes:** estrutura de dados e relacionamentos do domínio
- **Pacotes:** organização em camadas e responsabilidades
- **Componentes:** arquitetura lógica modular do software
- **Implantação:** distribuição física na infraestrutura de TI

---

## ✨ Funcionalidades Principais

- 🔐 **Autenticação:** Login seguro com controle de perfil (Atleta / Operador)
- 🏃 **Inscrição de Atletas:** Inscrição em competições com validação de país por modalidade
- 🏟️ **Gestão de Competições:** Cadastro, alteração e cancelamento de eventos olímpicos
- 📍 **Alocação de Locais:** Reserva de espaços sem conflito de horário
- 🥇 **Registro de Resultados:** Registro de pódio com validação de atletas
- 📊 **Relatório de Medalhas:** Quadro de medalhas por país (ouro, prata e bronze)

---

## 🛠 Tecnologias Utilizadas

### ✏️ Modelagem / Diagramação

* **Linguagem de Diagramação:** [PlantUML](https://plantuml.com/)
* **Notação:** UML 2.x
* **Diagramas produzidos:** Caso de Uso, Classes, Pacotes, Componentes, Implantação

---

## 📖 Histórias de Usuário

| ID | Nome | Descrição | Critérios de Aceite |
|:---:|---|---|---|
| **US01** | **Autenticar** | Como usuário do sistema, quero realizar login com meu e-mail e senha, para que eu possa acessar as funcionalidades disponíveis para o meu perfil. | E-mail e senha devem ser validados. Credenciais inválidas retornam erro. Perfil correto é carregado (Atleta ou Operador). |
| **US02** | **Realizar Inscrição** | Como atleta, quero me inscrever em uma competição específica, para que eu possa participar da modalidade desejada representando meu país. | Atleta deve estar autenticado. Inscrição é bloqueada se o atleta já representa outro país na mesma modalidade. Inscrição confirmada aparece na lista da competição. |
| **US03** | **Visualizar Atletas Inscritos** | Como atleta, quero visualizar a lista de atletas inscritos em uma competição, para que eu possa acompanhar quem são meus competidores. | Atleta deve estar autenticado. Lista exibe nome e país de cada inscrito. Lista reflete o estado atual das inscrições. |
| **US04** | **Visualizar Resultados** | Como usuário, quero visualizar os resultados das competições realizadas, para que eu possa acompanhar o desempenho dos atletas e o quadro de medalhas. | Qualquer usuário autenticado pode visualizar. Exibe ouro, prata e bronze por competição. Exibe quadro de medalhas por país. |
| **US05** | **Gerenciar Competição** | Como operador, quero gerenciar as competições do sistema, para que eu possa cadastrar, alterar ou cancelar competições conforme necessário. | Apenas operador autenticado tem acesso. Operador pode cadastrar, alterar e cancelar. Ações retornam confirmação ou erro descritivo. |
| **US06** | **Cadastrar Competição** | Como operador, quero cadastrar uma nova competição informando modalidade, data, horário e local, para que os atletas possam se inscrever nela. | Todos os campos obrigatórios devem ser preenchidos. Data e horário não podem conflitar com outro evento no mesmo local. Competição cadastrada recebe status "ativa". |
| **US07** | **Alterar Competição** | Como operador, quero alterar os dados de uma competição existente, para que eu possa corrigir ou atualizar informações quando necessário. | Competição cancelada não pode ser alterada. Alteração de data/horário revalida conflitos de local. Dados atualizados são persistidos corretamente. |
| **US08** | **Cancelar Competição** | Como operador, quero cancelar uma competição cadastrada, para que atletas e locais sejam liberados quando o evento não puder ser realizado. | Competição já realizada não pode ser cancelada. Ao cancelar, local e inscrições são liberados. Status é atualizado para "cancelada". |
| **US09** | **Alocar Local** | Como operador, quero alocar um local para uma competição, para que o espaço físico esteja reservado sem conflitos de horário com outros eventos. | Local só pode ser alocado se estiver disponível na data e horário. Um local não pode abrigar duas competições simultâneas. Alocação é registrada na competição. |
| **US10** | **Registrar Resultados** | Como operador, quero registrar os resultados de uma competição informando os atletas classificados em primeiro, segundo e terceiro lugar, para que o quadro de medalhas seja atualizado corretamente. | Operador deve estar autenticado. Os três atletas do pódio devem ser distintos e inscritos na competição. Resultado reflete no quadro de medalhas. |
| **US11** | **Gerar Relatório de Medalhas** | Como operador, quero gerar um relatório de medalhas por país, para que o desempenho de cada nação nas Olimpíadas possa ser acompanhado. | Operador deve estar autenticado. Relatório exibe total de ouros, pratas e bronzes por país. Países são ordenados por desempenho. |
| **US12** | **Verificar Data e Horário** | Como sistema, devo verificar se a data e o horário de uma nova competição não conflitam com eventos já cadastrados, para garantir a integridade do calendário olímpico. | Verificação ocorre automaticamente ao cadastrar ou alterar competição. Conflito detectado bloqueia a operação com mensagem de erro. |
| **US13** | **Verificar Disponibilidade de Local** | Como sistema, devo verificar se o local escolhido está disponível na data e horário solicitados, para que um mesmo espaço não seja alocado para duas competições simultâneas. | Verificação ocorre automaticamente ao alocar local. Local ocupado bloqueia a alocação com mensagem de indisponibilidade. |
| **US14** | **Validar Pódio** | Como sistema, devo validar que os três atletas registrados no pódio são distintos e participaram da competição, para garantir a integridade dos resultados registrados. | Validação ocorre automaticamente ao registrar resultados. Atletas repetidos ou não inscritos bloqueiam o registro. |
| **US15** | **Verificar País Representado** | Como sistema, devo verificar se o atleta já representa outro país na mesma modalidade antes de confirmar sua inscrição, para garantir que cada atleta represente apenas um país por modalidade. | Verificação ocorre automaticamente ao realizar inscrição. Conflito de país bloqueia a inscrição com mensagem de erro. |

---

## 🏗 Arquitetura e Diagramas

O sistema foi modelado com arquitetura em camadas, separando responsabilidades entre **Apresentação**, **Negócio** e **Dados**, com o padrão **Facade** centralizando o acesso aos serviços de domínio.

| Diagrama | Visualização |
| :---: | :---: |
| **Diagrama de Caso de Uso** | **Diagrama de Classes** |
| <img src="https://github.com/arthurgvv/Sistema-de-Gestao-das-Olimpiadas-Projeto-de-Software/blob/main/imagens/diagrama-de-caso-de-uso.png" alt="Diagrama de Caso de Uso" width="500px"/> | <img src="https://github.com/arthurgvv/Sistema-de-Gestao-das-Olimpiadas-Projeto-de-Software/blob/main/imagens/diagrama-de-classes.png" alt="Diagrama de Classes" width="500px"/> |
| **Diagrama de Pacotes** | **Diagrama de Componentes** |
| <img src="https://github.com/arthurgvv/Sistema-de-Gestao-das-Olimpiadas-Projeto-de-Software/blob/main/imagens/diagrama-de-pacotes.png" alt="Diagrama de Pacotes" width="500px"/> | <img src="https://github.com/arthurgvv/Sistema-de-Gestao-das-Olimpiadas-Projeto-de-Software/blob/main/imagens/diagrama-de-componentes.png" alt="Diagrama de Componentes" width="500px"/> |
| **Diagrama de Implantação** | |
| <img src="https://github.com/arthurgvv/Sistema-de-Gestao-das-Olimpiadas-Projeto-de-Software/blob/main/imagens/diagrama-de-implantacao.png" alt="Diagrama de Implantação" width="500px"/> | |

---

## 📂 Estrutura de Pastas

```
.
├── README.md
├── codigos/
│   ├── diagrama-de-caso-de-uso.puml
│   ├── diagrama-de-classes.puml
│   ├── diagrama-de-pacotes.puml
│   ├── diagrama-de-componentes.puml
│   └── diagrama-de-implantacao.puml
└── imagens/
    ├── diagrama-de-caso-de-uso.png
    ├── diagrama-de-classes.png
    ├── diagrama-de-pacotes.png
    ├── diagrama-de-componentes.png
    └── diagrama-de-implantacao.png
```

---

## 🔗 Documentações Utilizadas

* 📖 **PlantUML:** [Documentação Oficial](https://plantuml.com/guide)
* 📖 **PlantUML - Deployment Diagram:** [plantuml.com/deployment-diagram](https://plantuml.com/deployment-diagram)
* 📖 **PlantUML - Component Diagram:** [plantuml.com/component-diagram](https://plantuml.com/component-diagram)
* 📖 **PlantUML - Class Diagram:** [plantuml.com/class-diagram](https://plantuml.com/class-diagram)
* 📖 **PlantUML - Use Case Diagram:** [plantuml.com/use-case-diagram](https://plantuml.com/use-case-diagram)

---

## 👥 Autores

| 👤 Nome | 🖼️ Foto | :octocat: GitHub |
|---------|----------|-----------------|
| Arthur Gonçalves | <div align="center"><img src="https://github.com/arthurgvv.png" width="70px" height="70px" style="border-radius:50%"></div> | <div align="center"><a href="https://github.com/arthurgvv"><img src="https://joaopauloaramuni.github.io/image/github6.png" width="50px" height="50px"></a></div> |
| Matheus Guilherme | <div align="center"><img src="https://github.com/theuzao.png" width="70px" height="70px" style="border-radius:50%"></div> | <div align="center"><a href="https://github.com/theuzao"><img src="https://joaopauloaramuni.github.io/image/github6.png" width="50px" height="50px"></a></div> |

---

## 📄 Licença

Este projeto é distribuído sob a **Licença MIT**.

---
