# Challenge Backend - Blu

Bem vindo ao Code Challenge destinado as vagas de Engenheiro Backend da Blu!

Esse é um teste de nivelamento que é destinado à todos os níveis de carreira. Focamos aqui em design de código e design patterns. O objetivo é avaliar sua experiência em escrever código de fácil manutenção, baixo acoplamento e alta coesão.

O desafio consiste em desenvolver uma API Rest com o intuito de servir e persistir informações de perfil do médico, informações do usuário assim como permitir a criação de uma consulta.

## Requisitos mínimos (obrigatórios)

Esses são requisitos obrigatórios e devem ser cumpridos a fim de possibilitar que esse teste técnico seja devidamente avaliado.

### Funcionais

O candidato deve:

- Criar a rota _GET /accounts/doctor/:id_ que retorne o seguinte payload:

```json
{
  "doctor": {
    "address": {
      "fullAddress": {
        "placeId": "12312313",
        "description": "Ladeira da Cruz da Redenção, 659 - 659 - Candeal, Salvador - BA, 40296-190, Brazil"
      },
      "uf": "BA",
      "city": "Salvador",
      "district": "Candeal",
      "street": "Ladeira da Cruz da Redenção",
      "number": "659",
      "zipcode": "40296-190",
      "clinicName": "Clinica BBB"
    },
    "name": "Roberto Albuquerques",
    "email": "roberto@outlook.com",
    "imageUrl": "https://blu-s3-staging.s3.us-east-1.amazonaws.com/profile-images/57d4a2754b2f3eefedb99656131091b6-roberto.jpeg",
    "birthday": "1997-03-10T03:00:00.000Z"
  }
}
```

- Criar a rota _GET /accounts/patient/:id_ que retorne o seguinte payload:

```json
{
  "patient": {
    "name": "Roberto Albuquerques",
    "age": "26 anos",
    "imageUrl": "https://blu-s3-staging.s3.us-east-1.amazonaws.com/profile-images/57d4a2754b2f3eefedb99656131091b6-roberto.jpeg",
    "birthday": "1997-03-10T03:00:00.000Z"
  }
}
```

- Criar a rota _POST /appointments_ que receba o seguinte payload:

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

- Servir os arquivos estáticos através de uma cdn (S3, Cloudfront, etc)
- Adotar algum fluxo de autenticação

Os requisitos _técnicos_ opcionais incluem, não se limitando à:

- Adotar o padrão HATEOAS Restful
- Integrar a solução com algum serviço externo (utilizando uma API Rest, GraphQL ou qualquer outro paradigma de comunicação conveniente)
- Utilizar NodeJS, NestJS, Express ou qualquer outra biblioteca ou framework server-side JavaScript
- Adicionar swagger e configurar linters e formatadores
- Adicionar testes automatizados (sejam unitários, de integração ou end-to-end)
- Estabelecer uma configuração mínima e funcional de CI/CD
- Realizar o deploy da aplicação em algum servidor
- Dockerizar a app
