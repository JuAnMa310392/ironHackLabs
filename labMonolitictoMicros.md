
### Priorizar los Servicios a Migrar



1. **Servicio de Catálogo de Productos**
   - Este es crucial para el rendimiento y la escalabilidad.
2. **Servicio de Procesamiento de Pedidos**
   - También esencial para mantener un flujo de trabajo eficiente.
3. **Servicio de Gestión de Usuarios**
   - Importante para la autenticación y autorización.
4. **Servicio de Atención al Cliente**
   - Necesario para manejar consultas y quejas de los clientes.

### Identificar Dependencias

- **Servicio de Catálogo de Productos**
   - Depende de los datos de productos.

- **Servicio de Procesamiento de Pedidos**
   - Depende de los datos de usuarios y productos.

- **Servicio de Gestión de Usuarios**
   - Depende de la autenticación y autorización.

- **Servicio de Atención al Cliente**
   - Depende de los datos de usuarios y pedidos.

### Estrategia para la Migración de Datos

1. **Migrar Datos**
   - Mover datos a bases de datos específicas para cada servicio.

2. **Sincronización de Datos**
   - Implementar sincronización de datos durante la transición para evitar interrupciones en el servicio.

### Documentación de Arquitectura

### Arquitectura de Microservicios Propuesta

![335045864-0ae319b7-3e5f-4c2d-9a71-1967153cdbfd](https://github.com/user-attachments/assets/0e005f95-1be7-4a1b-b579-cbc3339eccb7)

### Narrativa de Decisiones Clave

#### Desacoplamiento de Servicios
- **Motivo:** Mejorar la escalabilidad, soporte y despliegue independiente de funcionalidades.

#### Uso de API Gateway
- **Motivo:** Facilitar la gestión centralizada de los request y proporcionar una capa de seguridad adicional y filtra request.

#### Base de Datos Separada por Servicio
- **Motivo:** Facilitar la escalabilidad y la independencia de datos para cada servicio, la concurrencia a datos se mitiga.

### Pasos de Migración

#### Preparación
1. Analizar el código monolitico existente.
2. Planificar la infraestructura necesaria para soportar los microservicios.
3. Crear flujos de negocio, para saber el numero de microservicios a crear
4. Validar BD de monolitico, para empezar a separar la información

#### Desarrollo del API Gateway
1. Implementar un API Gateway para gestionar las solicitudes entrantes asi como filtrar los request

#### Migración de Servicios
1. Migrar el **Servicio de Productos** y desplegarlo.
2. Migrar el **Servicio de Pedidos** y desplegarlo.
3. Migrar el **Servicio de Usuarios** y desplegarlo.
4. Migrar el **Servicio de Customer support** y desplegarlo.

#### Transición de Datos
1. Migrar datos a las nuevas bases de datos específicas de cada servicio.
2. Iniciar la operación con las nuevas bases
3. Asegurar la sincronización de datos entre las bases de datos antiguas y nuevas durante la transición.

#### Pruebas y Validación
1. Tener los contratos o swagger de los request de cada microservicio
2. Realizar pruebas de carga para validar el performance
3. Validar la integridad y consistencia de los datos.
4. Generar pruebas unitarias e integrales

#### Despliegue y Monitoreo
1. Desplegar los microservicios en producción.
2. Implementar herramientas de monitoreo y alertas para asegurar la estabilidad y el rendimiento de los servicios.
3. Tener un area de soporte a la proudcción para estabilizar el sistema
4. Se recomendaria tener alguna bandera que pueda decidir si el flujo se va por poryecto legacy o nuevos micros
   
