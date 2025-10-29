
## 🏗️ Arquitectura General

| Componente             | Tecnología elegida                      | Función principal |
|------------------------|------------------------------------------|-------------------|
| Frontend               | Next.js (React SSR)                      | Interfaz web para emisión y consulta |
| Backend                | NestJS (Node.js)                         | API RESTful + lógica de negocio |
| Base de datos          | MongoDB Atlas                            | Almacenamiento de facturas, clientes, productos |
| Firma electrónica      | OpenSSL + certificado digital            | Firmar documentos XML/PDF |
| Comunicación con MH    | API SOAP/REST del Ministerio             | Envío en tiempo real |
| Almacenamiento seguro  | Firebase Storage                         | Conservación de documentos por 15 años |
| Despliegue frontend    | Vercel                                   | Hosting del cliente Next.js |
| Despliegue backend     | Render                                   | Hosting del servidor NestJS |
| Panel administrativo   | Next.js + Tailwind CSS                   | Gestión de usuarios, reportes, auditoría |

- Firebase Admin SDK para subir y recuperar archivos
- Mongoose como ORM para MongoDB
- Axios o GraphQL para comunicación entre Next y Nest
- OpenSSL para firma digital en el backend
- Zod o Joi para validación de datos fiscales
