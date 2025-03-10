# Mi Proyecto

# Microservicio de Transacciones Financieras

Este microservicio es parte de un desafío técnico que implementa la validación de transacciones financieras utilizando un servicio antifraude y enviando mensajes a Kafka para actualizar el estado de las transacciones.

## Funcionalidades

- Valida transacciones financieras según criterios antifraude.
- Envía mensajes a Kafka para actualizar el estado de las transacciones.
- Maneja tres estados de transacción: pendiente, aprobado y rechazado.
- Permite crear nuevas transacciones y recuperar información sobre transacciones existentes.

## Tecnologías Utilizadas

- **Node.js**: Plataforma de tiempo de ejecución de JavaScript.
- **Express**: Framework web para Node.js.
- **Kafka**: Plataforma de streaming distribuido.
- **Sequelize**: ORM (Object-Relational Mapping) para Node.js.
- **PostgreSQL**: Sistema de gestión de bases de datos relacional.



## Instalación

1. Clona este repositorio en tu máquina local.
2. Instala las dependencias ejecutando el comando `npm install`.

## Configuración de Kafka

Asegúrate de tener un servidor Kafka en ejecución en `localhost:9092`.

## Ejecución

1. Ejecuta el comando `node app.js` para iniciar el servidor.
2. El servidor estará disponible en `http://localhost:3000`.

## Ejecución de Pruebas

1. Ejecuta el comando `npx jest` para ejecutar las pruebas unitarias.
2. Asegúrate de tener un entorno de Kafka de prueba configurado para ejecutar pruebas de integración.

## Endpoints

### Crear Transacción

- Método: POST
- Ruta: `/api/transactions`
- Cuerpo de la solicitud:
  ```json
  {
     "accountExternalIdDebit": "Guía",
     "accountExternalIdCredit": "Guía",
     "transferenciaTypeId": 1,
     "valor": 120
  }

  ### Actualización del Estado de una Transacción

Permite actualizar el estado de una transacción específica identificada por su ID.

#### Método

- **PUT**

#### Ruta

- `/api/transactions/{transactionId}/state`

#### Parámetros de Ruta

- `transactionId`: Identificador único de la transacción a actualizar.

#### Parámetros de Solicitud

- `state`: Nuevo estado de la transacción. Puede ser uno de los siguientes valores: pendiente, aprobado, rechazado.

#### Ejemplo de Solicitud

```json
PUT /api/transactions/12/state
{
  "state": "aprobado"
}



