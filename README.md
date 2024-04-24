# Challenge Backend - Blu

Bem vindo ao Code Challenge destinado às vagas de Engenheiro Backend da Blu!

Esse é um teste de nivelamento que é destinado à todos os níveis de carreira. Focamos aqui em design de código e design patterns. O objetivo é avaliar sua experiência em escrever código de fácil manutenção, baixo acoplamento e alta coesão.

O desafio consiste em desenvolver uma API Rest com o intuito de servir e persistir informações de perfil do médico, informações do usuário assim como permitir a criação de uma consulta.

## Requisitos mínimos (obrigatórios)

Esses são requisitos obrigatórios e devem ser cumpridos a fim de possibilitar que esse teste técnico seja devidamente avaliado.

### Funcionais

O candidato deve:

- Criar a rota _GET /accounts/doctor/:id_ que consulte os detalhes de um médico a partir de um `DoctorId` e retorne o seguinte payload:

```json
{
  "doctor": {
    "address": {
      "uf": "BA",
      "city": "Salvador",
      "district": "Stiep",
      "street": "Travessa Guaricema ",
      "number": "853",
      "zipcode": "41770-700",
      "clinicName": "Clinica Antidoto"
    },
    "name": "Roberto Albuquerques",
    "email": "roberto@outlook.com",
    "profileImageUrl": "https://blu-s3-staging.s3.us-east-1.amazonaws.com/profile-images/57d4a2754b2f3eefedb99656131091b6-roberto.jpeg",
    "birthday": "1987-07-10T03:00:00.000Z"
  }
}
```

- Criar a rota _GET /accounts/patient/:id_ que consulte os detalhes do paciente a partir de um `patientId` e retorne o seguinte payload:

```json
{
  "patient": {
    "name": "Leonardo Souza",
    "age": "37 anos",
    "profileImageUrl": "https://blu-s3-staging.s3.us-east-1.amazonaws.com/profile-images/57d4a2754b2f3eefedb99656131091b6-roberto.jpeg",
    "birthday": "1987-04-14T03:00:00.000Z"
  }
}
```

- Criar a rota _POST /appointments_ que cadastre uma nova consulta medica e receba o seguinte payload:

```json
{
  "patientId": "string",
  "doctorId": "string",
  "complaints": "string[]",
  "diagnosis": "string"
}
```

### Não funcionais

- Concluir o desafio utilizando a linguagem em que o candidato mais se sentir confortável fazendo o máximo uso possível das boas práticas. A entrega pode ser feita através de um respositório git ou em uma pasta zipada e enviada para o e-mail da equipe da Blu.

## Requisitos adicionais (opcionais)

Esses são requisitos opcionais. Eles não precisam ser cumpridos e não possuem caráter eliminatório, todavia, a depender da senioridade do candidato, eles podem se tornar obrigatórios pois oferecem um panorama mais completo com relação às suas habilidades.

Os requisitos _funcionais_ opcionais incluem, não se limitando à:

- Servir os arquivos estáticos (foto de perfil,  por exemplo) através de uma cdn (S3, Cloudfront, etc)
- Adotar algum fluxo de autenticação
- Adicionar validações aos formulários
- Desenvolver outros endpoints/features pertinentes 

Os requisitos _técnicos_ opcionais incluem, não se limitando à:

- Adotar o padrão HATEOAS Restful
- Integrar a solução com algum serviço externo (utilizando uma API Rest, GraphQL ou qualquer outro paradigma de comunicação conveniente)
- Utilizar NodeJS, NestJS, Express ou qualquer outra biblioteca ou framework server-side JavaScript
- Adicionar swagger e configurar linters e formatadores
- Adicionar testes automatizados (sejam unitários, de integração ou end-to-end)
- Estabelecer uma configuração mínima e funcional de CI/CD
- Realizar o deploy da aplicação em algum servidor
- Dockerizar a app
