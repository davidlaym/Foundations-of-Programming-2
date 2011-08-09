# Fundamentos de Programación 2 #
> "Si al principio no resulta, intenta, intenta, intenta otra vez" - William E. Hickson

## Licencia ##
Fundamentos de Programación 2 está bajo la licencia Attribution-NonCommercial 3.0 Unported. **Este libro no le debiera haber costado dinero**

Eres libre de copiar, distribuir, modificar y/o compartir el libro. Sin embargo, solicito que siempre atribuyas este libro a mí, Karl Seguin, y que no lo uses para propósitos comerciales.

Puedes ver el texto completo de la licencia en:
<http://creativecommons.org/licenses/by-nc/3.0/es/legalcode.es>

## Última Revisión ##
Este libro está actualmente en desarrollo, el lanzamiento final está esperado para inicios de Febrero de 2011

Para obtener la última versión, visita <http://github.com/karlseguin/foundations2>.

## Acerca del Autor ##
Karl Seguin es un desarrollador con experiencias en varios campos y tecnologías. Es un experto desarrollador en .Net y aprendiendo Ruby. Es familiar con todos los aspectos de el desarrollo web, concurrencia y programación de Sockets y varias tecnologías SQL y NOSQL. Es un contribuyente semi-activo de proyectos de código abierto, escritor técnico y un exponente esporádico.

Su blog puede ser accedido desde <http://openmymind.net>, y sus tweets via [@karlseguin](http://twitter.com/karlseguin)

El es también el fundador de servicios gratuitos para desarrolladores de juegos en <http://mogade.com>.

## Acerca del Traductor ##
David Lay es un desarrollador con experiencia principalmente en .Net con deseos de aprender y continuar aprendiendo otros paradigmas y plataformas. Ha diseñado, implementado y mantenido varios sistemas de linea de negocio, tanto web como escritorio. Está en una activa búsqueda por más entendimiento y siempre interesado en conocer personas que desafien sus puntos de vista y que le enseñen una o dos cosas (ojalá más).

## Introducción ##
Siempre me encuentro sorprendido por el número de programadores con los que me encuentro. Mucho de sus vidas lo dedican al trabajo del cual somos afortunados por tener la oportunidad de estar haciendo lo que amamos. Esta no es una propiedad única de los programadores, pero es lo suficientemente extraña para que la mayoría de la gente lo encuentre sorprendente. "¿Vas a casa y *trabajas* cada día?" nos preguntan. Solo nuestros más cercanos amigos y colegas apasionados entienden que *trabajo* tiene dos significados para nosotros, ninguno de los que es una esclavitud de 9 a 5.

Probablemente has notado que el entusiasmo y puje es una característica critica en un campo tan joven. La tecnología continúa cambiando a un paso acelerado, el campo está creciendo y los sistemas están cada día volviéndose más complejos. El resultado es una clara división entre programadores que aman su oficio y lo que no. Estas o bien leyendo, intentando y a veces fallando, o estás estancado en el pasado, probablemente ignorante de lo atrás que te has quedado.

Desafortunadamente, ser apasionado por lo que haces no siempre es suficiente. Todos tenemos distintas fortalezas y debilidades, diferentes formas de aprender y diferentes tolerancias al fallo. También tenemos el constante flujo de nuevas tecnologías que hacen difícil decidir en cual ocupar el tiempo para aprender. La verdad es que no soy un gran programador. Soy un buen programador que le gusta aprender (y enseñar) y que disfruta jugando con la tecnología. He visto personas aprender un lenguaje solo días cuando a mi me ha costado meses, o escribir algoritmos con los cuales pretendo estar de acuerdo porque simplemente no pude entenderlo. Las Fundaciones de la Programación es una serie pensada para ayudar a la gente como yo, gente a la que le interesa lo que hacen y lo queren hacer mejor, pero no están seguros como hacerlo.

Espero que este libro te ayude.

### Respecto al Original ###
El libro original [Foundations of Programming](https://github.com/karlseguin/Foundations-of-Programming-Ebook) ha sido, bajo mis estándares, un éxito. Tal parece haber ayudado genuinamente a desarrolladores y servido a una real necesidad cada libro, el original y este, existen por separado. Son independientes el uno del otro. Sin embargo podría sugerir que si tienes en mente leer el original, lo hagas antes de continuar con este. Mis vistas han madurado y en algunos casos cambiado o clarificado. Creo que mucho puede ser obtenido en ver cómo he evolucionado en la programación.

## Capítulo 1 - Calidad y Eficiencia ##
>"La calidad nunca es un accidente, siempre es resultado de un esfuerzo inteligente" - John Ruskin

Pragmáticamente, la razón por la que yo y (asumo) la mayoría de los programadores, estamos deseosos de aprender, es para mejorar la calidad del código que escribimos al igual que nuestra eficiencia. No conozco programador que ocupe tiempo aprendiendo nuevos acercamientos y tecnologías  con el objetivo explícito de escribir peor código, o encontrar medios para trabajar más lento. Pero, ¿Cómo medimos la eficiencia y la calidad? ¿Qué cosa, como creadores, consideramos que son nuestros objetivos?

Aquellos del tipo administrativo, considerarían como medida de calidad puramente la satisfacción del cliente. Aun cuando es ciertamente importante, los buenos programadores son los interesados con mayores expectativas y también son los más críticos. Como DeMarco y Lister dijeron en Peopleware, **Todos tendemos a vincular fuertemente nuestra auto estima con la calidad del producto que producimos - no con la cantidad del producto, sino con la calidad.** Encuentro difícil poder expresar con palabras, desde la perspectiva de un programador, lo que significa la calidad; pero, estoy seguro que no solo muchos de nosotros coincidimos en la definición, sino que también podemos reconocerla fácilmente (o la falta de ella). Calidad es sobre encontrar una solución elegante para un problema - tanto a un nivel micro (comportamientos individuales) como macro (el sistema como un todo). ¿Qué es *elegante* entonces? Varía según el contexto del problema pero, generalmente, una solución elegante es tanto la más simple posible, como la más explícita y fácil de entender.

Mientras más programo, más me doy cuenta de algo realmente sorprendente. No solo la solución más sencilla es obviamente la más fácil de implementar, sino que también la más fácil de entender, mantener y cambiar. Las soluciones simples también tienden a tener mejor rendimiento que aproximaciones más complejas. Esto es particularmente sorprendente cuando te encuentras hasta las rodillas en un lío sobre trabajado en donde la intención original de flexibilidad, rendimiento y eficiencia son saboteadas por complejidad artificial. Esto no significa que esté a favor de la programación sin consideración por el diseño. En vez, creo que dada cierta experiencia y reflexión, un balance entre pensar por delante los problemas y el pragmatismo no solo es lograble, sino que también bastante natural.

Me gustaría decirte cuál es la respuesta. No es que no lo sepa. El problema es que tengo que anteponer una advertencia; sino corro el riesgo que me des un desprecio y dejes el libro aquí. Yo sé que muchos de ustedes está cansados de escucharlo, pero les suplico que me escuchen y reconozcan que probablemente no estoy diciendo lo que ustedes piensan que digo. ¿Ok? Entonces, el secreto para escribir código con calidad es asegurarse de que el código es testeable. ESPERA... no te vayas aun. No estoy diciendo que debas testear tu código (Ciertamente tampoco niego que se deba hacer) solo estoy diciendo que si, teóricamente, fueras a testear tu código, no debiera ser difícil. El código puede ser testeable sin efectivamente testearlo y al final, es a lo que debieras apuntar.

Por un largo tiempo pensaba que la solución era realmente así de simple. Escribir tests y la calidad del código iría incrementando. Pero más recientemente me he dado cuenta que no todos los tests son creados iguales y que es enteramente posible, si es que no común, tener realmente malos tests. Entender qué es lo que hace a un tests bueno, y por lo tanto qué es lo que hace al código testeable, viene con la experiencia y espero, junto con los siguientes capítulos, pueda ayudarte a esquivar algunas de las piedras que me he encontrado en el camino. Es por esto que mucho de este libro estará dedicado tanto a escribir tests como a la testeabilidad del código. No mezcles testeabilidad como una métrica con escribir tests. Es como escribir un montón de código mantenible que no necesita mantenimiento. Es un objetivo, no una actividad. Ahora, es cierto que la mejor manera de descubrir que una solución es testeable es mediante la escritura de un test. Eso sí, espero poder convencerte de que le des un intento; en los últimos tres años el convertirme en un escritor de tests efectivo es una de las cosas que más me ha ayudado a elevar mi habilidad. Sin embargo, es enteramente posible ver un método o un sistema y estimar su testeabilidad, y por lo tanto, su calidad, sin escribir un test.

### Testeabilidad como una medida de calidad ###
No te culpo si eres escéptico. Todo lo que puedo hacer es prometer que mientras puede se que gastemos algo de tiempo escribiendo tests, no voy a tratar de hacerte sentir que estás haciendo algo malo si elijes no hacer tests. También, puedo mostrarte un ejemplo sencillo de lo que quiero decir:

	//Un ejemplo de código difícil de probar, y por lo tanto, de mala calidad.
	private void LoginButton_Click(object sender, EventArgs e)
	{
		User user = SqlServerDataStore.FindUser(UserName.Text, Password.Text);
		if (user != null)
		{
			Session["userId"] = user.Id;
			Response.Redirect("~/members/index.aspx");
		}
		else
		{
			ErrorMessage.Text = "Invalid UserName or Password";
		}
	}
(Si esta fuera una pequeña aplicación desechable, podríamos perdonarla. Aunque también debo decir que en mi experiencia, programadores hábiles escriben código limpio sin importar la expectativa de vida para el código. Esto es probablemente por el hecho que todos conocemos código de *prototipos* que ha terminado con un periodo de vida vergonzosamente largo.)
 
Este trozo de código está lejos de la perfección. Si específicamente lo miramos desde una perspectiva de la testeabilidad, podemos ver una cantidad de dependencias que lo harán difícil de testear, como por ejemplo `SqlServerDataStore.FindUser` y `Response.Redirect`, por nombrar algunas. Lamentablemente muchas de estas vienen incluidas en el framework, lo que es uno de los motivos por los que muchos programadores .Net tienen tan fuertes sentimientos en contra de WebForms. En este caso en particular, la práctica imposibilidad de hacer tests me dice que este código va a ser difícil de cambiar y mantener.

Muchas de las mejores prácticas que escuchas por ahí, como YAGNI (you aren't going to need it; no lo vas a necesitar), bajo acople y alta cohesión, puede ser medido mediante la observación del código y pensando cómo lo testearías. Un método que hace demasiado, potencialmente está violando tanto YAGNI como la alta cohesión, y requerirá una cantidad dolorosa de código inicial en un test, y probablemente va a ser muy fácil de quebrar.

Hay un acrónimo  en la programación que se usa bastante: SOLID. Se refiere a cinco principios importantes del diseño orientado a objetos: Single responsibility principle (Principio de responsabilidad única), Open/close principle (Principio abierto/cerrado), Liskov substitution principle (Principio de substitución de Liskov), Interface segregation principle (Principio de segregación de interfaces) y Dependency inversion principle (Principio de inversión de dependencias). Estos son todos tópicos dignos de su propio capítulo, pero deberá bastar decir que muchos de ellos son algo ambiguos. ¿En qué momento un nuevo comportamiento o mejora es considerado una responsabilidad o en cuál se le asigna un componente? ¿Cuándo una interfaz se vuelve demasiado compleja? Estas son preguntas importantes y respuestas equivocadas van a tener consecuencias. La testeabilidad y la experiencia son herramientas que puedes usar para resolver esta ambigüedad. (Un buen lugar para comenzar a aprender sobre SOLID es en la <a href="http://en.wikipedia.org/wiki/Solid_(object-oriented_design)">Wikipedia</a>.)

### Eficiencia: No tan simple como parece ###
Puede que aún no me creas sobre la testeabilidad como métrica de calidad, pero confío en que crees que la calidad es un aspecto de suprema importancia. Otro de nuestros objetivos pragmáticos es la eficiencia, debido a que no debemos demorarnos mucho en producir un código de gran calidad. Uno esperaría que la eficiencia en cuanto a aprender y mejorar, fuera algo fácil de medir: puedo lograr XYZ ahora más rápido de lo que lo hacía antes, pero no es así.

Primero que nada, y lo más peligroso, es que los programadores no siempre nos damos cuenta de que hay mejores formas de hacer las cosas. Seamos honestos, muchos de los programadores rehúsa aceptar solo la posibilidad que exista. Es difícil para la gente, especialmente aquellos no muy apasionados sobre lo que hacen, el aceptar que hay mejores formas de hacer las cosas. No solo amenaza su comodidad, pero potencialmente sus carreras. Yo estaba en la escuela cuando Java iniciaba a ganar popularidad y quedé impresionado por lo cerrado de mente de los programadores que rehusaban aceptar que la recolección de basura automática, luego de corregir algunos menores problemas, podría ser algo muy útil (ni pensar en estándar). Ahora encuentro particularmente irónico ver programadores de Java reusando aceptar que los lenguajes dinámicos podrían convertirse en el nuevo Java (Especialmente dado que generalmente utilizan los mismos argumentos que los que usaban los programadores C++ contra Java)

Segundo, sin importar cuanto más eficiente es una tecnología o técnica, siempre serás más eficiente en lo que sabes versus lo que estás aprendiendo. Mi estrategia para sobrepasar esto es tomarme mi tiempo y reconocer que el proceso es una inversión de largo plazo. Además si eres astuto, probablemente puedas introducir algo de investigación en tu trabajo diario. Por astuto no quiero decir tramposo. Quiero decir que encuentres un proyecto secundario, no crítico. Aquel sistema de monitorización que querías hacer pero que nunca tuviste tiempo, o aquel prototipo que te solicitaron hacer. La aproximación exacta que tomes va a depender de tu forma de aprender. Todo lo que puedo decir es que no debieras esperar un incremento de productividad de la noche a la mañana.

### En Este Capítulo ###
Eso fue mucho texto y poco código. Este capítulo sentó las bases para los que continúan, los que presentarán mucho código y ejemplos. Definimos lo que significa calidad para nosotros así como las métricas que usaremos para medirlo (testeabilidad). Miramos a la eficiencia y descubrimos que mientras parecía fácil de medir, no lo era. Toma un respiro y considera algo del código que has escrito recientemente. Si hiciste tests, ¿Qué podría haber hecho los tests más simples y que tuvieran menor posibilidad de fallar si el sistema cambia? Si no lo hiciste, ¿Puedes imaginar algún inconveniente o problema que enfrentarías si decidieras hacer tests ahora?

## Capítulo 2 - Otra Introducción más a IoC ##
> "El propósito de la ingeniería de software es controlar la complejidad, no crearla." - Pamela Zave

Dependiendo de que tecnología uses, La Inversión de Control (IoC por sus siglas en inglés) y la Inyección de Dependencias (DI por sus siglas en inglés) puede o no que sean algo en lo que pases leyendo o inviertas energía. En algunos lenguajes, IoC y DI juegan un rol explícito en el desarrollo. En otros, es casi invisible. Eso no significa que IoC es menos importante o fundamental en algunos lenguajes que en otros. Lo que es diferente es el mecanismo usado para lograr IoC, que es lo realmente fascinante del asunto y es el por qué iremos a invertir un par de capítulos aprendiendo sobre esto.

Nuestro plan es iniciar con una corta introducción a IoC en este capítulo, luego examinaremos el problema de distintas perspectivas. El propósito no es etiquetar una aproximación como mejor que otra, sino que expandir como vemos y nos enfrentamos a un desafío central que constantemente encontramos al programar. Cuando finalmente pude ver IoC más allá del estrecho entendimiento mediante el cual fui introducido, un nuevo mundo se abrió a mis ojos.  No porque este sea un conocimiento que sacuda la tierra - de hecho quizás ni siquiera cambie tu forma de programar. Lo que hizo por mí fue validar la importancia de expandir mi conocimiento más allá de mi zona de comodidad. Me mostró lo ignorante que era (y aun soy), y saber que eres ignorante es la clave para ser un programador exitoso.

### Unas palabras sobre Acoplamiento ##
Antes que iniciemos a examinar IoC, vamos a entender el problema que estamos tratando de solucionar. El acoplamiento es lo que obtienes cuando algo depende de otra cosa. Esa otra cosa puede ser una asignación, un método, una clase o incluso un sistema completo. Por ejemplo:

	#Incluso el código más simple nos pueda acoplar a otra clase o implementación:
	time = Time.now
	
	//...Algo un poco más complejo
	$('#logs').load('/orders/history', {id: _id});
	
	//...O algo mucho más grande
	var richList = Session.Query<Account>().Where(a => a.Amount > 10000000).List();


En cada uno de los ejemplos anteriores, nuestro código es dependiente de alguna otra implementación. Praáticamente toda linea de código que escribas, técnicamente  hablando, va a generar acoplamiento. Gran parte del tiempo el acoplamiento es benigno (Nadie sugiere que realices envolturas para cada librería o dependencia), sin embargo casos más complejos terminan fácilmente en problemas de testeabilidad, lo que indica que el código es difícil de modificar y mantener. El último ejemplo es más obvio, dado que es imposible hacer tests sin efectivamente llegar a la base de datos (aunque hablaremos de esto en futuros capítulos ya que ir a la base de datos en un test no es para nada una mala idea).

El tipo de acoplamiento fuerte que queremos evitar es el que introduce dependencias entre componentes o sistemas. Incluso cuando sabes que la implementación no va a cambiar, el acoplamiento hará difícil el refactoring y el mantenimiento.

### Bases de la Inversión de Control ###
Si el acoplamiento (que X sea dependiente de Y) es el problema, entonces la Inversión del control es la solución. IoC es un término que engloba carias soluciones que nos ayudan a desacoplar, o cuando menos, reducir el acoplamiento. La idea general es cambiar el flujo procedural por algo en lo cual se tenga mayor control. Para mejor entender el concepto, veamos la forma más común de IoC en .Net: Inyección de Dependencias (DI).

El nombre *Inyección de Dependencias* dice mucho de lo que la técnica permite: Inyectar dependencias en nuestro código en vez de definirlas de manera estática (en duro). Estamos examinando primero esta forma de IoC no porque sea la más simple o sea la mejor, pero porque el resultado es particularmente explícito y debido a que es una aproximación independiente del lenguaje, del framework o la tecnología que estemos usando.

Un ejemplo:

	public class UserRepository
	{
		public User FindByCredentials(string username, string password)
		{
			var user = SqlDataStore.FindOneByNamedQuery("FindUserByUserName", new {username = username});
			if (user == null) { return null; }
			return BCrypt.CheckPassword(user.Password, password) ? user : null;
		}
	}

Este código tiene dos dependencias de las que haríamos bien de desacoplarnos. La primera es `SqlDataStore` y la otra `BCrypt`. La idea detrás de la Inyección de Dependencias es tomar estas dos dependencias y administrarlas hacia nuestra clase o método, en vez de tenerlas en duro. Esto puede ser logrado pasándolas como argumentos a nuestro método, estableciendo propiedades en nuestra clase, o mediante el método más común: entregarlas al constructor de la clase como argumentos. Cada aproximación tiene sus propias ventajas y desventajas, pero todas proveen el mismo beneficio: externalizan la dependencia y en un mondo de tipos estáticos, se puede programar contra interfaces. Aquí vemos el ejemplo anterior re-escrito con Inyección de dependencia al nivel del constructor:

	public class UserRepository : IUserRepository
	{
		private IDataStore _store;
		private IEncryption _encryption;
		public UserRepository(IDataStore store, IEncryption encryption)
		{
			_store = store;
			_encryption = encryption;
		}
		
		public User FindByCredentials(string username, string password)
		{
			var user = _store.FindOneByNamedQuery("FindUserByUserName", new {username = username});
			if (user == null) { return null; }
			return _encryption.CheckPassword(user.Password, password) ? user : null;
		}	
	}

(Para dar un ejemplo completo hemos hecho que `UserRepository` implemente una interfaz también, de esa manera puede ser injectada hacia el código que la utiliza).


Nuestro código ahora nos escuda de la implementación directa, haciendo más fácil mantener, cambiar y probar la funcionalidad. También, mientras algunos puedan encontrar que el método `FindByCredentials` ahora es un poco más difícil de entender (con lo que estoy de acuerdo), si realmente te pones a pensar, vas a encontrar que la clase `UserRepository` como un todo es más entendible. Puedes fácilmente mirar el constructor de `UserRepository` y entender *cómo* logra lo que hace. Otro beneficio, del cual hablaremos más adelante, es que la Inyección por constructor ayuda a mantener nuestras clases cohesivas (a tener un propósito acotado y bien definido) - ya que al tener muchas dependencias generalmente significa que la clase está haciendo demasiadas cosas.

Del ejemplo anterior debiera ser evidente cómo se verían las injecciones mediante propiedad o método. Inyectar a un método es útil solo cuando ese método tiene una dependencia específica (pero debiera ser usado de manera muy esporádica ya que un uso muy frecuente indica falta de cohesión entre la clase y los métodos). La Inyección mediante propiedades es ideal para dependencias opcionales (Que también son bastante raras). La Inyección mediante propiedad es también útil para el código interno de los frameworks, donde deseas que las clases que hereden no necesiten tener constructores muy complejos.

### Frameworks de Inyección de Dependencias ###
En las comunidades donde DI es un patrón común, los frameworks de DI son abundantes y muy populares, por lo que haremos de esta mención algo breve. Lo que necesitas saber es que el ejemplo que presentamos previamente, cuando es hecho de manera manual, puede añadir una cantidad considerable de sobrecarga a nuestra programación. Si nuestro código desde la interfaz de usuario hasta los servicios externos (bases de datos, servicios web, etc) tiene 4 o 5 niveles de profundidad y nuestras clases en promedio tienen 1 a 3 dependencias, entonces instanciar y rastrear nuestros objetos no va a ser muy divertido.

Es en este pundo donde los frameworks de Inyección de dependencia entran al juego. Los configuras con las dependencias que necesitas usar y luego dejas que el framework los administre y se preocupe de crear los objetos. Puedes pensar en ellos como en una súper fábrica de objetos, que puede darse cuenta cuales son los servicios que una clase necesita y se los administra de manera automática, para entregarte una clase y todo su árbol de dependencias creado y listo para usar. 

Veremos ahora un ejemplo de esto utilizando [Ninject](http://ninject.org/). La primera cosa que haremos es configurar nuestro framework DI. Los detalles de como se hace varían de un framework a otro. Ninject utiliza una configuración fluida.

	private sealed class BoostrapDependencyModule : NinjectModule
	{
		public override void Load()
		{
            //Cuando pida un IUSerRepositoury, entrega una clase UserRepository
			Bind<IUserRepository>().To<UserRepository>();
            
            //Cuando pida un IDataStore, entrega un SqlDataStore
			Bind<IDataStore>().To<SqlDataStore>();
				
			//Cuando pida un IEncryptor, entrega un Encryptor,
            //pero siempre entregame el mismo (Singleton)
			Bind<IEncryptor>().To<Encryptor>().InSingletonScope();
		}
	}

Ahora podemos crear un kernell de Ninject y solicitarle instancias::

	var kernel = new StandardKernel(new BoostrapDependencyModule());
	var repository = kernel.Get<IUserRepository();

El framework DI verá que le solicitamos un ´IUserRepository´, entonces revisa en su configuración que necesita entregar un `UserRepository`. En ese momento, revisa el constructor y entiende que tiene dos dependencias. Nuevamente revisa su configuración y encuentra estas dependencias, así que las crea y las inyecta, y de esta forma es capaz de entregarnos una instancia lista para usar.

Mantén en mente que el objetivo de un framework DI no es hacer el código dinámicamente enlazable. Queremos ser capaces de programar contra interfaces injectadas donde sea necesario. Es algo que podemos hacer de manera manual, pero incluso ejemplos simples son un verdadero dolor. Un framework DI automatiza una pequeña pero importante parte del proceso (Creación de objetos con dependencias).

Es difícil dejar pasar la oportunidad para quejarse por las configuraciones basadas en XML, así que... La mayoría de los frameworks de DI en .Net proveen tanto configuraciones por código (como la que vimos arriba) como configuraciones mediante XML. El beneficio de usar configuraciones por código es que tienes la capacidad de refactorizar y testear tus configuraciones. No hay ninguna ventaja con configuraciones en XML, aunque algunos programadores argumentarán que con XML no necesitan recompilar para cambiar una dependencia. Yo digo que esos es basura: Un cambio en una configuración de dependencia, independiente de donde se almacene, amerita el mismo proceso de QA y publicación que cualquier otro cambio en la aplicación.

### Anti patron de Inyección de Dependencias ###
Finalizar nuestra introducción a Inyección de dependencias con lo que hemos cubierto hasta ahora sería desfavorable. Hemos cubierto las mecánicas de DI y los frameworks de DI, pero al enfocarnos en el *que* hemos introducido algunos feos *como*. Nuestra instancia de  `kernel` del ejemplo anterior es thread-safe, y podríamos crear una clase estática y llamarla algo como `Factory.Get<T>` en todas partes de nuestro código. Como sugerimos arriba, los frameworks de DI pueden verse como una suplantación de el keyword `new`, así que podría ser una buena aproximación. 
	

Usar nuestro framework de DI de esta forma es conocido como el patrón Service Locator, pero es generalmente percibido como un anti-patrón. Uno necesita limitar el uso directo del framework DI. Si estás usando un framework moderno, debieran haber puntos en los cuales puedas introducir la resolución de dependencias mediante el framework DI. Por ejemplo. ASP.NET MVC 1 y 2 permiten que proveas un controller factory personalizado, que puede ser usado como punto de inicio para la resolución de dependencias (La versión 3 tiene un modelo aun más simple) De hecho, la mayoría de los frameworks DI proveerán estas extensiones para diversos Frameworks, como es el caso del `NinjectHttpApplication` de ninject,  del cual simplemente heredas y le configuras los modelos y listo. Como un check simple, revisa cuantas veces estás importando el namespace de tu framework DI. No debieras encontrarlo en más de 4 o 5 lugares.
El punto es que con lenguajes de tipos estáticos, los frameworks de DI debieran ser un ejercicio solo de configuración que de programación. Puede que te encuentres llamando al kernell de manera directa en las partes más bajas de tu código, pero la resolución de dependencias automática debiera encargarse de ese punto en adelante. Si tu framework de DI no permite realizar esto, cambia el framework por uno más potente.

### En este Capítulo ###
En este capítulo hemos visto que es Inversión de Control como también el problema que estamos tratando de solucionar (reducción de acoplamiento). También vimos un patrón común de IoC: la Inyección de dependencia. Para muchos programadores esta es una forma diferente de programar y pensar. En todo caso, recuerden que ganamos mucho de esto: El código es más fácil de cambiar y refactorizar, clases con baja cohesión son fáciles de descubrir y los tests son más fáciles de hacer.

## Capítulo 3 - IOC de cabeza ##
> "Si no elevas la mirada, vas a pensar que eres el punto más alto" - Antonio Porchia

Al comenzar el aprendizaje de IoC y realizar los primeros experimentos con un framework de DI, nunca te preguntas si hay otra forma de resolver dependencias. DI es bastante simple y a la vez hace juego con la forma en que la mayoría de la gente organiza su código .Net o Java. DI es un patrón adecuado para programación orientada a objetos en lenguajes estáticos... pero cambia a un paradigma diferente y encontrarás soluciones diferentes.

### Cambio de mente dinámico ###
Es común para los desarrolladores pensar que los lenguajes dinámicos y el tipado dinámico son sinónimos. Es cierto que muchos (pero no todos) los lenguajes dinámicos tienen un sistema de tipos dinámico. Pero el hecho es que los lenguajes dinámicos realizan muchas cosas en tiempo de ejecución que en un lenguaje estático se hacen al momento de compilar. La implicancia es que con un lenguaje dinámico los desarrolladores tienen mayores capacidades en tiempo de ejecución que sus contrapartes estáticas.

Al principio este poder extra puede verse como de poca utilidad. Después de todo, ¿Qué tan frecuentemente necesitas cambiar el código en tiempo de ejecución? Bueno, como es en la mayoría de los casos, no sabemos lo que necesitamos hasta que lo tenemos a disposición y luego nos preguntamos qué hacíamos antes de tenerlo. Piénsalo en términos de las características añadidas a C# con el paso del tiempo: tipos genéricos (Generics), métodos anónimos, LINQ (por nombrar algunos). Un runtime dinámico es lo mismo, el impacto es difícil de comprender mientras estés restringido por tus experiencias en lenguajes estáticos. Reflection no es una parte integral de tu código porque es limitado y complicado; pero si fuera poderoso y simple probablemente sería una herramienta que utilizarías día a día (para ser honesto, comparar los lenguajes dinámicos con Reflection es tremendamente injusto para los lenguajes dinámicos, pero solamente estamos tratando de establecer algunos paralelos)

¿Qué tiene esto que ver con la Inversión de Control? La naturaleza flexible de los lenguajes dinámicos significan que IoC está directamente implementado en la mayoría de los lenguajes dinámicos. No hay necesidades de inyectar parámetros o usar frameworks. Simplemente utiliza las capacidades del lenguaje. Veamos un ejemplo:

	class User
	  def self.find_user(username, password)
	    user = first(:conditions => {:username => username})
	    user.nil? || !Encryptor.password_match(user, password) ? nil : user
	  end
	end
    
Nuestro código tiene dos dependencias: `first` va a acceder a un almacenaje subyacente (lo que puede que no sea obvio si no eres familiar con Ruby) y `Encryptor` es una clase inventada para comparar el hash del password del usuario junto con el entregado. En un mundo estático ambos serían complicados. En Ruby y otros lenguajes dinámicos es simplemente asunto de cambiar la implementación de `first` y `Encryptor`:

	def password_match_returns(expected)
		metaclass = class << Encryptor; self; end
		metaclass.send :define_method, :password_match do
			return expected
		end
	end
  
	def first_returns(expected)
		metaclass = class << User; self; end
		metaclass.send :define_method, :first do
			return expected
		end
	end
    
Mantén una mente abierta y recuerda que este código puede ser tan misterioso para ti como métodos anónimos y lambdas para otras personas. Discutiremos el código en más detalle pero primero miraremos a cómo es utilizado:

	it "returns the found user" do
	  user = User.new
	  first_returns(user)
	  password_match_returns(true)
	  User.find_user('leto', 'ghanima').should == user
	end
    
En la vida real utilizarías un framework de mocking para que se haga cargo de esto y que provea una sintaxis más limpia y otras características más poderosas. Pero, haciendo a un lado un poco de magia, podemos ver que nuestros dos métodos redefinen los métodos `first` y `password_match` en tiempo de ejecución para que implementen un comportamiento que nuestros test pueden utilizar. Para realmente iniciar a entender esto necesitaremos cubrir clases "Singleton" (de solo una instancia).

#### Singleton y Metaclases ####

En C#, Java y muchos de los demás lenguajes estáticos, una clase puede seguramente verse como una plantilla rígida. Uno define campos y métodos y compila el código usando las clases como un contrato inmutable. Las clases sirven un propósito muy útil como una herramienta de diseño. El problema de las clases, sin ser culpa de ellas, es que muchos desarrolladores piensan que las clases y la programación orientada a objetos son una y la misma. No lo son. La programación orientada a objetos, como el nombre indica, es acerca de los objetos. En lenguajes estáticos esto significa instancias. Dado que las instancias están fuertemente ligadas con su respectiva clase, es fácil entender por qué los desarrolladores mezclan los conceptos.

Pero si miras más allá de los lenguajes estáticos y veras una historia distinta. No solo no hay ley que diga que las clases no puedan ser entes vivos por sí mismos, sino que también verás que la programación orientada a objetos puede existir felizmente sin clases. El mejor ejemplo con el que probablemente ya eres familiar es JavaScript. Contempla la POO sin clases:
 
	var leto = {
		fullName: 'Leto Atreides II',
		title: 'Emperor',
		yearOfBirth: 10207,
		getAngryWithDuncan: function(duncan) {
			duncan.alive = false;
		}
	};
	
	var duncan = {
		ghola: true,
		alive: true
	};
	
	leto.getAngryWithDuncan(duncan);
   
Como siempre, el punto no es que una forma es mejor que la otra, sino obtener distintas perspectivas. Si haces POO de una sola forma por mucho tiempo, terminarás comprometiendo tu capacidad para crecer como profesional.

Si bien la orientación a objetos no *requiere* de clases, son muy útiles como plantillas. Es en este punto donde Ruby y las clases singleton brillan; porque como lo hemos mencionado, no hay ley que diga que una clase no pueda cambiar.

En Ruby todo objeto tiene su propia clase, llamada una clase singleton. Esto te permite definir miembros en instancias específicas, por ejemplo:

	class Sayan
		# our class defition for a Sayan
	end
	
	goku = Sayan.new
	vegeta = Sayan.new
	
	def goku.is_over_9000?
		true #in ruby, the last executed statement is automatically returned
	end
	
	p goku.is_over_9000?  	=> true
	p vegeta.is_over_9000?	=> NoMethodError: undefined method `is_over_9000?'

Técnicamente no estamos añadiendo el método `is_over_9000?` al objeto `goku`, sino que lo estamos agregando a la clase singleton oculta de la cual el objeto `goku` hereda y por lo tanto tiene acceso. Decimos que la clase singleton es invisible porque tanto `goku.class` y `vegeta.class` retornan `Sayan`. Hay formas de exponer la clase singeton, pero cuando no estás haciendo metaprogramación, las clases singleton son transparentes.

Para obtener acceso a la clase singleton, que es en si un objeto real, usamos la sintaxis `class << ` syntax. Por ejemplo, el método `is_over_9000?` podría ser definido de la siguiente manera:

	class << goku
		def is_over_9000?
			true
		end
	end
    
Si queremos asignar la clase singleton a una variable, podemos simplemente exponer `self`:

	singleton = class << goku
		self
	end
	
	#o más comun y conciso, usando ; en vez de saltos de línea
	singleton = class << goku; self; end

Interesantemente (y no estoy seguro de porqué lo encuentro interesante), si observamos a las instancias `goku` and `singleton` obtenemos el siguiente resultado:

	goku
	=> #<Sayan:0x10053a1f0>
	singleton
	=> #<Class:#<Sayan:0x10053a1f0>>

En Ruby, todo es un objeto, incluso una clase es un objeto (que hereda de `Class`, que a su vez hereda de `Object`). Esto significa que puedes invocar métodos en tus clases:

	Sayan.is_a?(Object)
	=> true
	Sayan.is_a?(Integer)
	=> false
	Sayan.to_s
	=> "Sayan"
    
 Dado que las clases son objetos, también tienen clases singleton (que generalmente son llamadas metaclases). Podemos tener acceso a la metaclase de una clase mediante la misma sintaxis anterior `class <<`:
 
	metaclass = class << Sayan
		self
	end
	#or, the more consice approach
	metaclass = class << Sayan; self; end

Las clases Singleton no son realmente algo con lo que estarás trabajando muy seguido, pero son importantes porque los métodos de las clases son definidos en sus metaclases. Los métodos de una clase son muy similares a los métodos estáticos en lenguajes como C# o Java. Son definidos en dos posibles formas y son usados de la forma que esperarías:

	class Sayan
		# Primera forma de definir un método de clase, usando self.nombreDeMetodo
		def self.find_most_powerful()
		  # todo
		end
		
		# segunda forma, mediante la metaclase
		class << self
			def all_by_level(superSayanLevel)
				# todo
			end
		end
	end
	
	powerfulSayans = Sayan.all_by_level(3)
 
(Entender `self` en Ruby, especialmente lo que `self` representa en distintos contextos, es importante para aprender el lenguaje)

La diferencia clave entre los métodos de clase en Ruby y los métodos estáticos en Java/C# es que las los métodos de clase son definidos en la metaclase que es un objeto. Dicho de otra forma, mientras los métodos de clase puedan parecerse a métodos estáticos, son en realidad más similares a métodos de instancia.

¿Qué sacamos de todo esto? Mucha de la rigidez que encontrarás en un lenguaje estático no existe en un lenguaje dinámico. Clases selladas, metodos no virtuales y métodos estáticos, que son mecanismos para prevenir que hagas ciertas cosas, desaparecen. Hay pros y contras a cada paradigma, pero no hay razón para dejar de conocer a cada uno.

Quiero, eso si, dejar claro que desde el punto de vista de la capacidad de prueba, tiene muchas ventajas. - la dificultad de probar un método estático `password_match` en C# debiera ser prueba suficiente de que no podemos simplemente sobrescribir la implementación como hicimos en el inicio del capítulo, simplemente porque las clases no son objetos. DI, o siquiera las interfaces no son necesarias en Ruby. El desacople que se logra en C# mediante inyección de interfaces y administración de dependencias es reemplazado por la propia naturaleza del lenguaje Ruby.

### Eventos / Callbacks ###
Otra forma de reducir el acoplamiento es utilizando eventos y callbacks. Es bien conocido que los eventos, por su propia naturaleza, proveen protección contra el acoplamiento. El código que lanza un evento declara *no me interesa quien eres o lo que vas a hacer, pero es tiempo de hacerlo.* Puede haber 0 manejadores, o cientos y pueden hacer un conjunto de cosas sin relación entre ellas, pero nada de eso le importa a quien lanza el evento. El código termina siendo fácil de probar ya que desde el punto de vista del emisor, solo tienes que probar que el evento ha sido emitido y desde el punto de los interesados, que el método ha sido subscrito.

La razón por la cual no usamos eventos en todas partes es porque simplemente no se ajustan al flujo lineal que usamos para la mayoría de nuestro código. Sin embargo, en los últimos años esto ha empezado a cambiar. ¿Por qué? El renacer de JavaScript. Ahora tenemos mucho más código en JavaScript y muchos programadores están abandonando sus percepciones (generalmente negativas) y aprendiendo el lenguaje. JavaScript ya no es un lugar en donde baste confiar en hacks y esperar que todo siga funcionando. Ha habido un cambio hacia un JavaScript de calidad y mantenible. Esto significa que necesitamos comenzar a preocuparnos del acoplamiento, la cohesión y la testeabilidad. Cuando se trata de aquello, eventos son en JavaScript lo que DI es para Java/C# o metaprogramación es para Ruby.

Digamos que eres un maestro de [jQuery](http://www.jquery.com/) (si no lo eres, puedes saltar al Apendice A y B para iniciar esa jornada cuando quieras) y has construido una cantidad de plugins. Estas son cosas que planeamos reusar a lo largo de nuestro sitio. Muchas de estas plugins van a necesitar  interactuar con las demás. Por ejemplo, una de las plugins convierte una simple lista de filas en una rejilla ordenable y paginable y otra permite que un formulario sea enviado mediante AJAX. Por supuesto, cuando el usuario envía un nuevo registro mediante el formulario AJAX, la rejilla debe actualizarse. Primero veamos la configuración básica:

	// aplica el plugin fancyGrid al elemento con el id users
	$('#users').fancyGrid();
	
	// aplica el plugin fancySubmit al elemento con el id add_user
	$('#add_user').fancySubmit();

El centro de nuestra plugin `fancySubmit` sería algo tan simple como:

	(function($) 
	{
	  $.fn.fancySubmit = function(options)
	  {
	    return this.each(function()
	    {
	      var $form = $(this);
	      var self = 
	      {   
	        initialize: function() 
	        {
         		$form.submit(function()
         		{
         			$.post($form.attr('action'), $form.serialize(), self.handleResponse);
         			return false;	
         		});
	        },
	        handleResponse: function(r)
	        {
	        	//what to do here?
	        }
	      };
	      this.fancySubmit = self;
	      self.initialize();      
	    });
	  };
	})(jQuery);

(Si jQuery no te es familiar, este código está interceptando el evento `submit` del formulario para enviar los datos mediante AJAX. La respuesta es luego manejada por la función `handleResponse`. Nuevamente, quizás quieras saltar a los Apéndices A y B para tomar velocidad en jQuery.)

`handleResponse` puede manejar casos genéricos (errores, validación) directamente, pero cualquier cosa más específica va a depender del contexto en el cual esté siendo usado. ¿La solución? Permitir que un callback sea entregado al plugin y llamarlo cuando sea tiempo.

	handleResponse: function(r){
		// agregar aquí (quizás) algún manejo generico
		if (options.onSubmit != null) { options.onSubmit(r); }
	}

Con este cambio tan simple ahora podemos enlazar las dos plugins sin que una sepa de la otra:

	// Aplica el plugin fancyGrid al elemento con el plugin users
	var $users = $('#users').fancyGrid();
	
	// Aplica el plugin fancySubmit al elemento con el id add_user
	$('#add_user').fancySubmit({
		onSubmit: function(r) { $users.fancyGrid('newRow', r); }
	});

Usando esta forma, las dos plugins trabajan juntas sin saber nada una de la otra. esto ayuda a asegurar que tu código se mantenga altamente reusable y cohesivo.

### Poniendolo a prueba ###
Podemos probar `handle response` entregando un callback falso que pueda hacer algunas verificaciones básicas. Sin embargo, debemos asegurarnos en llamar a `$.post`. Debido a que JavaScript es dinámico como Ruby, también provee mecanismos para cambiar nuestras definiciones en tiempo de ejecución. Combinando nuestra reimplementacion dinamica con nuestros callbacks personalizados obtenemos:

	test("ejecuta el callback onSubmit luego de recibir una respuesta", function()
	{
		expect(1); // ignora esto por ahora

		// Sobreescribe el metodo $.post para que siempre ejecute el callback con la respuesta preparada
		$.post = function(url, params, callback) 
		{ 
			callback('the new row'); 
		}

		var $form = $('#a_test_form');
		$form.fancySubmit(
		{
			onSubmit: function(r) 
			{ 
				ok(r == 'the new row', 'callback with response was called'); 
			}
		});

		$form.submit();
	});

Ignora la llamada a `expect` por ahora, llegaremos a eso en un minuto. Reimplementamos la función `$.post`, evadiendo la pesada implementación real con algo más manejable. `$.post` esencialmente solo ejecuta el tercer parámetro (que si recordamos, arriba en el plugin, es una llamada a `self.handleResponse`) con parametros preestablecidos. Luego, inicializamos el plugin con nuestro callback, el cual va a asegurar que el parámetro entregado sea el que esperamos. Finalmente enviamos el formulario para ejecutar el código real.

Acerca el llamado a `expect`, esto le dice a nuestro framework, [Qunit](http://docs.jquery.com/Qunit) en este caso, que debe esperar una llamada al método. Esto es lo principal cuando se trabaja con callback y eventos. ¿Qué podria pasar si no llamamos `expect` y además modificamos nuestro plugin para no llamar al callback? Todavií pasaríamos esta prueba porque nunca nada sería asegurado. Especificando `expect(1)` nos aseguramos que nuestra expectativa real (que nuestro callback sea llamado una vez, no más ni menos, y con los parámetros correctos) es invocada. Si `ok` no es llamado, entonces `expect` va a fallar y sabremos que algo anda mal.

La introducción de métodos anónimos y lamdas hacen posible que se escriba código similar en c#, que aveces es incluso mejor que lo que normalmente se escribe.

### En este Capítulo ###

Dependiendo de tu experiencia con Ruby y jQuery, este capítulo puede haber sido sobrecogedor. Cubrimos algunos conceptos avanzados en lenguajes que son menos familiares para nosotros. Posiblemente elegimos la parte más complicada de Ruby para meter nuestras narices (metaprogramación), así que no te desanimes si algo (o mucho) se te ha escapado. También vimos algunos escenarios de pruebas bien distintos. Más importante, en todo caso, fue como pudimos volver a aprender algo que ya conocíamos bien (IoC) explorando cosas que para otras personas, son fundamentales. Con confianza puedes considerar IoC como una característica incluida en Ruby, de manera muy similar a como se puede ver que LINQ es una característica incluida en C#. Incluso si no entiendes las complicaciones de el codigo o las implicaciones que tiene en la programación cotidiana, este capítulo puede aún mostrar el valor de aprender y crecer.