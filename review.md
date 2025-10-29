# Sistema de Gestión de Facturas Electrónicas - El Salvador

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

---

## 🔐 Módulos Clave

- Autenticación con JWT y roles (admin, contador, auditor)
- Gestión de clientes y productos (CRUD con validaciones fiscales)
- Generación de factura electrónica:
  - Formato XML/PDF
  - Firma digital
  - Envío al Ministerio
  - Almacenamiento en Firebase
- Historial y auditoría de acciones
- Panel administrativo con reportes y exportación

---

## 🔄 Flujo de Emisión de Factura

1. Usuario crea factura desde Next.js
2. NestJS valida y genera el documento
3. Se firma digitalmente
4. Se envía al Ministerio de Hacienda
5. Se guarda en MongoDB Atlas y Firebase Storage

---

## 🔌 Integraciones Sugeridas

- Firebase Admin SDK para subir y recuperar archivos
- Mongoose como ORM para MongoDB
- Axios o GraphQL para comunicación entre Next y Nest
- OpenSSL para firma digital en el backend
- Zod o Joi para validación de datos fiscales
