# Google Cloud Platform Fundamentals: Core Infraesctructure  
GCP ofrece cuatro tipos de servicios:  
- Procesamiento.  
- Almacenamiento.  
- Macrodatos.  
- Aprendizaje automático.  
**¿Qué es la computación en la nube?**  
La definición la creó el Instituto de Normas y Tecnologías de EE.UU.  
La computación en la nube es una forma de usar TI que tiene cinco caracteristicas importantes.  
- Primero los recursos de procesamiento son a pedido y con autoservicio. Solo se debe usar una interfaz simple y se obtendrá toda la potencia de procesamiento, almacenamiento y redes que necesite sin necesidad de intervención humana.  
- Segundo, accederá a estos recursos por la red desde dónde desee.  
- Tercero, el proveedor de estos recursos tiene un gran grupo de ellos y se los asigna a los clientes desde ese grupo. El cliente no tiene que conocer ni preocuparse por la ubicación exacta de estos recursos y el precio es razonablemente menor.  
- Cuatro, los recursos son elásticos. Si se necesitan más recursos, se pueden obtener de manera rápida, si se necesitan menos, se pueden reducir.  
- Cinco, los clientes solo pagan por lo que usan o reservan  

Los centros de datos virtualizados, introdujeron la **infraestructura como servicio (IaaS)** y la **plataforma como servicios (PaaS)**.  
- **IaaS** proporciona procesamiento, almacenamiento y redes sin procesar organizados de formas que conocemos por los centros de datos.  
- **PaaS** vincula el código de la aplicación que escribe a las bibliotecas que dan acceso a la infraestructura que necesita su aplicación. De este modo, puede enfocarse
solo en la lógica de la aplicación. En el modelo IaaS, paga por lo que asigna. En el modelo PaaS, paga por lo que usa.  
Ambos superan la forma antigua en la que compraba todo por adelantado basado en muchas previsiones riesgosas. Con la evolución de la computación en la nube el impulso cambió hacia la infraestructura
y los servicios administrados. GCP le ofrece muchos servicios en los que no tendrá que preocuparse por el aprovisionamiento de recursos.  
- **SaaS** Las aplicaciones populares de Google, como la Búsqueda, Gmail, Documentos y Drive son aplicaciones de software como servicio ya que las consumen los usuarios finales
directamente en Internet.  

Según algunas estimaciones públicas la red de Google envía 40% del tráfico mundial de Internet cada día. La red de Google es la más grande de su tipo en el planeta. Está diseñada para dar a los usuarios
la mayor capacidad de procesamiento y la menor latencia posible para sus aplicaciones. La red se interconecta en más de 90 intercambios de Internet y más de 100 puntos de presencia en todo el mundo. Cuando un usuario de Internet envía tráfico a 
un recurso de Google Google responde la solicitud del usuario desde una ubicación perimetral de red que proporcionará la menor latencia posible. La red de almacenamiento en caché perimetral cita contenido cerca del usuario para minimizar la latencia.  

**Organización GCP**
Comencemos por el mayor nivel de detalle: la zona, que se muestra a la derecha. Una zona es un área de implementación para los recursos de Google Cloud Platform. Por ejemplo cuando inicia una máquina virtual en GCP
mediante Compute Engine que veremos más adelante se ejecuta en una zona que usted especifica. Aunque los usuarios creen que la zona es como un centro de datos de GCP esto no es exacto ya que una zona no siempre se corresponde
con un único edificio físico. Sin embargo, puede visualizar una zona de esa forma. Las zonas se agrupan en regiones, áreas geográficas independientes y puede elegir en qué regiones
se encontrarán sus recursos de GCP. Todas las zonas de una región tienen conectividad de red rápida entre ellas. Las ubicaciones en una región suelen tener
latencias de red de ida y vuelta de menos de cinco milisegundos. Piense en una zona como un único dominio de falla dentro de una región. Como parte de compilar
una aplicación tolerante a errores puede distribuir sus recursos a lo largo de varias zonas de una región. Esto ayuda a evitar errores inesperados. Además, puede ejecutar los recursos
en diferentes regiones. Muchos clientes de GCP hacen eso tanto para acercar sus aplicaciones a usuarios de todo el mundo como para protegerse contra la pérdida de una región completa a causa, por ejemplo, de un desastre natural. Muchos servicios de Google Cloud Platform
permiten colocar recursos en lo que denominamos una Multi-Región. Por ejemplo, Google Cloud Storage, que abordaremos más adelante le permite colocar datos dentro de la Multi-Región de Europa. Es decir que se almacenan de forma redundante en, al menos, dos ubicaciones geográficas separadas por, al menos,
160 km dentro de Europa. Al momento de la producción de este video, GCP tiene 15 regiones.  

**Impacto ambiental**
El mundo virtual está hecho en una infraestructura física y todos esos bastidores de servidores usan grandes cantidades de energía. Todos los centros de datos existentes usan
alrededor del 2% de la electricidad mundial. Por eso, Google busca que los centros de datos sean lo más eficiente posible. Los centros de datos de Google, fueron los primeros en obtener la certificación ISO 14001 una norma que determina un marco de trabajo para mejorar la eficiencia de recursos y reducir desechos. Este es el centro de datos de Google
en Hamina, Finlandia uno de los centros de datos más avanzados y eficientes de la flota de Google. Su sistema de enfriamiento usa agua de mar de la bahía para reducir el uso de energía. Es el primero de su tipo en el mundo. Google es uno de los mayores compradores corporativos de energía eólica y solar Desde 2007 no produce emisiones de carbono y pronto alcanzará un 100%
de fuentes de energía renovables para sus centros de datos.  

**Precios**  
Google fue el primer gran proveedor de servicios en la nube en ofrecer facturación por segundo para su oferta de procesamiento en infraestructura como servicio: Google Compute Engine. La facturación detallada reduce mucho los costos de las cargas de trabajo inestables,
que son muchas. Muchos de los servicios más conocidos de GCP se facturan por segundo incluidos Compute Engine y Kubernetes Engine. Sabrá más de estos y otros servicios en este curso. Compute Engine ofrece
descuentos por uso continuo que se aplican automáticamente. Son descuentos automáticos que obtiene por ejecutar una instancia de máquina virtual durante una parte significativa del mes de facturación. Es decir, cuando ejecuta una instancia
durante más del 25% de un mes Compute Engine le da un descuento automático por cada minuto incremental que use para esa instancia. Las máquinas virtuales personalizadas de Compute Engine le permiten ajustar las máquinas virtuales
para sus aplicaciones lo que, a su vez, le permite personalizar los precios para sus cargas de trabajo.  

**Seguridad de varias capas**  
Tanto las placas de servidor
como los equipos de red de los centros de datos de Google tienen diseños personalizados. Google también diseña chips personalizados que incluyen un chip de seguridad de hardware llamado Titan que actualmente se implementa
en servidores y periféricos. Las máquinas de servidor de Google usan firmas criptográficas para garantizar que inicien el software correcto. Google diseña y construye sus propios centros de datos que incorporan varias capas
de protección de seguridad física. El acceso a los centros de datos se limita a una pequeña fracción de empleados de Google.  
Un procedimiento remoto llamado datos en la red que es como los servicios de Google se comunican entre sí. La infraestructura encripta el tráfico de PC en tránsito entre centros de datos. El servicio central de identidad de Google que se manifiesta a los usuarios finales
como la página de acceso de Google no solo pide un nombre de usuario y contraseña. También desafía de forma inteligente a los usuarios para corroborar información basada en factores de riesgo como si accedieron con el mismo dispositivo
o desde una ubicación similar en el pasado. Los usuarios también pueden usar un segundo factor cuando acceden incluyendo dispositivos basados en el estándar abierto de segundo factor universal, U2F.  
Muchas aplicaciones en Google acceden indirectamente al almacenamiento físico mediante servicios de almacenamiento y la encriptación está integrada en esos servicios. Permite compatibilidad con la encriptación
de hardware en discos duros y SSD. Así es como Google logra la encriptación en reposo de los datos de los clientes. Los servicios de Google que buscan estar disponibles en Internet se registran en una infraestructura de servicio llamada Google Front End que verifica conexiones de red entrantes
para certificados y prácticas recomendadas. Ademá, GFE aplica protecciones contra ataques de denegación del servicio. La sola escala de su infraestructura le permite a Google absorber muchos ataques de denegación del servicio incluso detrás de GFE. Google tiene protecciones contra denegación
del servicio de varios niveles y capas que reducen más el riesgo del impacto de la denegación del servicio. Dentro de la infraestructura de Google la inteligencia artificial y las reglas advierten sobre posibles incidentes. Google realiza ejercicios de Red Team ataques simulados para mejorar
la efectividad de sus respuestas. Google limita agresivamente y supervisa de forma activa las actividades de los empleados que reciben acceso de administrador a la infraestructura. Para evitar ataques de phishing contra los empleados, sus cuentas deben usar claves de seguridad compatibles con U2F. Para asegurarse de que el código sea lo más seguro posible Google almacena en central su código fuente y requiere revisión de dos partes del código nuevo.  

### Introducción a GCP  
Cuando se ejecutan cargas de trabajo en GCP, se utilizan proyectos para organizarlas. Usa Google Cloud Identity y Access Management también llamado IM o IAM, para controlar qué puede hacer quién.  
Los **proyectos** son la forma principal de organizar los recursos que usa en GCP. Se usan para agrupar recursos relacionados generalmente por un objetivo comercial en común.   
**Principio del menor privilegio:** Es importante al administrar todo tipo de infraestructura de computom ya sea en la nube o loca. El principio establece que, cada usuario debe tener solo los privilegios necesarios para hacer su trabajo.  

Los clientes de GCP usan IM para implementar el menor privilegio lo que beneficia a todos. Existen cautro maneras de interactuar con la capa de administración de GCP esto es, con la consola, basada en la web con el SDK y sus herramientas en línea de comandos , con las API y con una aplicación para dispositivos móviles.  

### Jerarquía de recursos de GCP  
Todos los recursos (VM, depósitos de Cloud Storage, tablas de BigQuey, etc). están organizados en proyectos. Lo proyectos pueden organizarse en carpetas. Y las carpetas pueden incluir más carpetas.  
Todas las carpetas y proyectos pueden juntarse en un nodo de organización.  
Las políticas puede definirse en proyectos, carpetas y nodos de organización. Estas se heredan hacia abajo en la jerarquía.  
Los proyectos son la base para habilitar y usar servicios de GCP como administrar API, habilitar la facturación agregar y quitar colaboradores, y habilitar otros servicios de Google. Cada proyecto es un compartimiento separado,
y cada recurso pertenece exactamente a uno. Los proyectos pueden tener diferentes propietarios y usuarios. Se compilan y se administran por separado. Cada proyecto de GCP tiene un nombre y un ID de proyecto que usted asigna. El ID es un identificador permanente, inalterable y único en todo GCP. Use los ID de proyecto en varios contextos para indicarle a GCP con qué proyecto desea trabajar.  
Las carpetas permiten que los equipos deleguen derechos administrativos para que puedan trabajar de manera independiente. Los recursos de una carpeta heredan políticas de IAM de la carpeta.
En general, los ID de proyecto son strings legibles que usará, con frecuencia, para hacer referencia a proyectos. Puede organizar los proyectos en carpetas, pero eso no es obligatorio. Son una herramienta disponible para simplificarle la vida.  
**Nodo:** Es el nivel superior de la jerarquía. Hay algunas funciones especiales asociadas. Por ejemplo, puede asignar un administrador de política de organización para que solo las personas con privilegios puedan cambiar las políticas. Además, puede asignar una función de creador de proyecto que es una buena manera de controlar quién puede gastar dinero.  
La herencia es transitiva,lo que significa que todos los recursos de los proyectos también la heredan. Hay una regla importante que debe tener en cuenta. Las políticas implementadas en un nivel superior de esta jerarquía no pueden quitar el acceso otorgado en un nivel inferior.  
#### Evaluación 4  
!(evaluacion4)[./img/evaluacion4.jpg]  

### Administración de identidades y accesos (IAM)  
IAM permite a los administradores autorizar quiénes pueden realizar acciones en recursos específicos. Se compone de:
- "Quién": Puede definirse con una cuenta de Google o un grupo, una cuenta de servicio, todo un dominio de G Suite o de Cloud Identity.  
- "Qué puede hacer":  Se define mediante la función de IAM.  
  **Función de IAM:** Es una colección de permisos. Hay tres tipos de funciones:  
  - Funciones básicas: Son amplias. Se aplican a un proyecto de GCP y afectan a todos los recursos de ese proyecto. Son propietario, editor y lector.  
   La función de propietario de un proyecto le permite hacer algo más configurar la facturación.  
   - Funciones especificas: GCP ofrece su propio conjunto de funciones predefinidas y definen en dónde se pueden aplicar.
-  "En qué recurso": A qué se le desea aplicacir la función.  

La función de **administrador** de instancias de Compute Engine permite ejecutar un conjunto de acciones determinado en máquinas virtuales. Las acciones son: enumerarlas, leer y cambiar su configuración, iniciarlas y detenerlas.
#### Evaluación 5  
!(evaluacion5)[./img/evaluacion5]  


