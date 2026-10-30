# NutriViandas – Sistema de Gestión de Pedidos e Insumos

Trabajo Práctico Integrador de **Organización Empresarial**
Tecnicatura Universitaria en Programación– Universidad Tecnológica Nacional (UTN)

## Descripción del sistema

**NutriViandas** es una empresa que elabora y distribuye viandas saludables para clientes particulares y corporativos. Su misión es ofrecer una alternativa práctica y nutritiva para quienes buscan comer bien en el día a día, con insumos de alta calidad.

El sistema documentado en este repositorio es un **módulo de software para la planificación de menús y el control de stock de insumos**. Sus funciones principales son:

- **Registrar las recetas** de cada vianda, con las cantidades exactas de cada insumo.
- **Descontar automáticamente el stock** cuando un pedido se confirma.
- **Deshabilitar en el catálogo** las viandas que no pueden elaborarse por falta de insumos.
- **Generar alertas de compra** cuando un insumo baja del stock mínimo.
- **Generar la lista de producción diaria** para la cocina.

El objetivo es reducir el desperdicio de insumos, evitar pedidos sin stock y agilizar los procesos de reposición.

## Integrantes

| Nombre | Rol |
|---|---|
| Mariano José Moreno Poggi | Autor (trabajo individual) |

**Docente titular:** Gabriela Martinez
**Docente tutor:** Pablo García

## Enlaces

- **Tablero ágil (Jira / GitHub Projects):** _(se completa al crear el tablero)_

## Estructura del repositorio

```
nutriviandas-documentacion/
├── README.md
└── docs/
    ├── entregas/     Entregas 1, 2 y 3 del trabajo práctico
    └── bpmn/         Diagrama BPMN del proceso de pedido
```

## Documentación

| Contenido | Ubicación |
|---|---|
| Entrega 1: La organización y su enfoque sistémico | [docs/entregas](./docs/entregas) |
| Entrega 2: Diagnóstico y planeación del proyecto tecnológico | [docs/entregas](./docs/entregas) |
| Entrega 3: Estructura formal y diseño de datos | [docs/entregas](./docs/entregas) |
| Diagrama BPMN del proceso de pedido | [docs/bpmn](./docs/bpmn) |

## Modelado del proceso (BPMN)

El diagrama modela el proceso **"Gestionar pedido de vianda"** con notación BPMN 2.0:

- **Pools:** Cliente y NutriViandas.
- **Lanes de NutriViandas:** Sistema (comportamiento automatizado), Cocina y Repartidor.
- **Flujo estándar:** recepción del pedido, verificación de stock, cobro (particular) o registro para facturación mensual (empresa), confirmación, descuento de insumos, lista de producción, elaboración y envío.
- **Excepciones contempladas:** falta de stock, pago no confirmado dentro de los 10 minutos y stock por debajo del mínimo.

**Alcance:** la emisión de la factura mensual a empresas queda a cargo de Contabilidad y está fuera del alcance del software. El sistema solo registra el pedido como pendiente de facturar.

## Control de versiones

El repositorio se trabaja con ramas secundarias y Pull Requests; no se realizan commits directos a `main` (salvo el commit inicial).

La revisión de los Pull Requests fue realizada por el propio autor por tratarse de un trabajo individual; los comentarios y correcciones quedan documentados en cada PR.

## Indicadores de control y estándares de desempeño

## Indicadores de control y estándares de desempeño

| # | Indicador | Fórmula | Estándar | Frecuencia | Fuente del dato | Justificación |
|---|---|---|---|---|---|---|
| 1 | Pedidos con inconvenientes por falta de stock | Cantidad de pedidos afectados por falta de stock en la semana | ≤ 1 por semana | Semanal | Pedidos cancelados o rechazados por stock | Meta de la Entrega 2; mide si el control de stock evita promesas que la cocina no puede cumplir. |
| 2 | Reducción del tiempo de revisión de stock | (tiempo manual anterior − tiempo actual) / tiempo manual anterior × 100 | ≥ 90% | Mensual | Medición comparativa antes y después | Meta de la Entrega 2; mide la ganancia de eficiencia por automatizar el control. |
| 3 | Latencia de deshabilitación de viandas sin stock | Tiempo entre que el stock de un insumo llega a 0 y la vianda deja de estar disponible | ≤ 2 segundos | En cada prueba y de forma continua | Logs del sistema | Meta de la Entrega 2; evita que un cliente pida un plato sin insumos. 
| 4 | Tiempo de respuesta al registrar un pedido | Tiempo entre el envío del pedido y su confirmación en pantalla | ≤ 3 segundos | En cada prueba | Pruebas de rendimiento y logs | Una respuesta lenta afecta la experiencia de atención al cliente. 
| 5 | Tiempo entre pago confirmado e ingreso a producción | Diferencia entre las marcas de tiempo de confirmación de pago y de ingreso a la lista de producción | ≤ 5 segundos | En cada prueba | Logs del sistema | Mide el grado de automatización del flujo modelado en el BPMN. |
| 6 | Alertas de stock mínimo atendidas a tiempo | Alertas resueltas antes del faltante / alertas generadas × 100 | ≥ 90% | Mensual | Registro de alertas y órdenes de compra | Mide si el área de abastecimiento repone antes de quedarse sin insumos. |


**Auditoría:** cada indicador se compara contra su estándar con la frecuencia indicada. Si se incumple, se registra el desvío y se define una acción correctiva.

## Declaración de Uso de IA

- Utilicé Claude para revisar y corregir el diagrama BPMN, para realizar la estructura de este readme.md, y para generar ideas sobre posibles indicadores de rendimiento.

La responsabilidad sobre la revisión, comprensión y entrega final del trabajo es
completamente mía.# NutriViandas – Sistema de Gestión de Pedidos e Insumos

Trabajo Práctico Integrador de **Organización Empresarial**
Tecnicatura Universitaria en Programación– Universidad Tecnológica Nacional (UTN)

## Descripción del sistema

**NutriViandas** es una empresa que elabora y distribuye viandas saludables para clientes particulares y corporativos. Su misión es ofrecer una alternativa práctica y nutritiva para quienes buscan comer bien en el día a día, con insumos de alta calidad.

El sistema documentado en este repositorio es un **módulo de software para la planificación de menús y el control de stock de insumos**. Sus funciones principales son:

- **Registrar las recetas** de cada vianda, con las cantidades exactas de cada insumo.
- **Descontar automáticamente el stock** cuando un pedido se confirma.
- **Deshabilitar en el catálogo** las viandas que no pueden elaborarse por falta de insumos.
- **Generar alertas de compra** cuando un insumo baja del stock mínimo.
- **Generar la lista de producción diaria** para la cocina.

El objetivo es reducir el desperdicio de insumos, evitar pedidos sin stock y agilizar los procesos de reposición.

## Integrantes

| Nombre | Rol |
|---|---|
| Mariano José Moreno Poggi | Autor (trabajo individual) |

**Docente titular:** Gabriela Martinez
**Docente tutor:** Pablo García

## Enlaces

- **Tablero ágil (Jira / GitHub Projects):** _(se completa al crear el tablero)_

## Estructura del repositorio

```
nutriviandas-documentacion/
├── README.md
└── docs/
    ├── entregas/     Entregas 1, 2 y 3 del trabajo práctico
    └── bpmn/         Diagrama BPMN del proceso de pedido
```

## Documentación

| Contenido | Ubicación |
|---|---|
| Entrega 1: La organización y su enfoque sistémico | [docs/entregas](./docs/entregas) |
| Entrega 2: Diagnóstico y planeación del proyecto tecnológico | [docs/entregas](./docs/entregas) |
| Entrega 3: Estructura formal y diseño de datos | [docs/entregas](./docs/entregas) |
| Diagrama BPMN del proceso de pedido | [docs/bpmn](./docs/bpmn) |

## Modelado del proceso (BPMN)

El diagrama modela el proceso **"Gestionar pedido de vianda"** con notación BPMN 2.0:

- **Pools:** Cliente y NutriViandas.
- **Lanes de NutriViandas:** Sistema (comportamiento automatizado), Cocina y Repartidor.
- **Flujo estándar:** recepción del pedido, verificación de stock, cobro (particular) o registro para facturación mensual (empresa), confirmación, descuento de insumos, lista de producción, elaboración y envío.
- **Excepciones contempladas:** falta de stock, pago no confirmado dentro de los 10 minutos y stock por debajo del mínimo.

**Alcance:** la emisión de la factura mensual a empresas queda a cargo de Contabilidad y está fuera del alcance del software. El sistema solo registra el pedido como pendiente de facturar.

## Control de versiones

El repositorio se trabaja con ramas secundarias y Pull Requests; no se realizan commits directos a `main` (salvo el commit inicial).

La revisión de los Pull Requests fue realizada por el propio autor por tratarse de un trabajo individual; los comentarios y correcciones quedan documentados en cada PR.

## Indicadores de control y estándares de desempeño

## Indicadores de control y estándares de desempeño

| # | Indicador | Fórmula | Estándar | Frecuencia | Fuente del dato | Justificación |
|---|---|---|---|---|---|---|
| 1 | Pedidos con inconvenientes por falta de stock | Cantidad de pedidos afectados por falta de stock en la semana | ≤ 1 por semana | Semanal | Pedidos cancelados o rechazados por stock | Meta de la Entrega 2; mide si el control de stock evita promesas que la cocina no puede cumplir. |
| 2 | Reducción del tiempo de revisión de stock | (tiempo manual anterior − tiempo actual) / tiempo manual anterior × 100 | ≥ 90% | Mensual | Medición comparativa antes y después | Meta de la Entrega 2; mide la ganancia de eficiencia por automatizar el control. |
| 3 | Latencia de deshabilitación de viandas sin stock | Tiempo entre que el stock de un insumo llega a 0 y la vianda deja de estar disponible | ≤ 2 segundos | En cada prueba y de forma continua | Logs del sistema | Meta de la Entrega 2; evita que un cliente pida un plato sin insumos. 
| 4 | Tiempo de respuesta al registrar un pedido | Tiempo entre el envío del pedido y su confirmación en pantalla | ≤ 3 segundos | En cada prueba | Pruebas de rendimiento y logs | Una respuesta lenta afecta la experiencia de atención al cliente. 
| 5 | Tiempo entre pago confirmado e ingreso a producción | Diferencia entre las marcas de tiempo de confirmación de pago y de ingreso a la lista de producción | ≤ 5 segundos | En cada prueba | Logs del sistema | Mide el grado de automatización del flujo modelado en el BPMN. |
| 6 | Alertas de stock mínimo atendidas a tiempo | Alertas resueltas antes del faltante / alertas generadas × 100 | ≥ 90% | Mensual | Registro de alertas y órdenes de compra | Mide si el área de abastecimiento repone antes de quedarse sin insumos. |


**Auditoría:** cada indicador se compara contra su estándar con la frecuencia indicada. Si se incumple, se registra el desvío y se define una acción correctiva.

## Declaración de Uso de IA

- Utilicé Claude para revisar y corregir el diagrama BPMN, para realizar la estructura de este readme.md, y para generar ideas sobre posibles indicadores de rendimiento.

La responsabilidad sobre la revisión, comprensión y entrega final del trabajo es
completamente mía.
