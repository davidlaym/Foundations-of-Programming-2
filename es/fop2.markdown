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

Por un largo tiempo pensaba que la solución era realmente así de simple. Escribir tests y la calidad del código iría incrementando. Pero más recientemente me he dado cuenta que no todos los tests son creados iguales y que es enteramente posible, si es que no común, tener realmente malos tests. Entender qué es lo que hace a un tests bueno, y por lo tanto qué es lo que hace al código testeable, viene con la experiencia y espero, junto con los siguientes capítulos, pueda ayudarte a esquivar algunas de las piedras que me he encontrado en el camino. Es por esto que mucho de este libro estará dedicado tanto a escribir tests como a la testeabilidad del código. No mezcles testabilidad como una metrica con escribir tests. Es como escribir un montón de código mantenible que no necesita mantenimiento. Es un objetivo, no una actividad. Ahora, es cierto que la mejor manera de descubrir que una solución es testeable es mediante la escritura de un test. Eso sí, espero poder convencerte de que le des un intento; en los últimos tres años el convertirme en un escritor de tests efectivo es una de las cosas que más me ha ayudado a elevar mi habilidad. Sin embargo, es enteramente posible ver un método o un sistema y estimar su testeabilidad, y por lo tanto, su calidad, sin escribir un test.

### Testeabilidad como una medida de calidad ###
No te culpo si eres escéptico. Todo lo que puedo hacer es prometer que mientras puede se que gastemos algo de tiempo escribiendo tests, no voy a tratar de hacerte sentir que estás haciendo algo malo si elijes no hacer tests. También, puedo mostrarte un ejemplo sencillo de lo que quiero decir:

	//Un ejemplo de código dificil de probar, y por lo tanto, de mala calidad.
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
 
Este trozo de código está lejos de la perfección. Si específicamente lo miramos desde una perspectiva de la testabilidad, podemos ver una cantidad de dependencias que lo harán difícil de testear, como por ejemplo `SqlServerDataStore.FindUser` y `Response.Redirect`, por nombrar algunas. Lamentablemente muchas de estas vienen incluidas en el framework, lo que es uno de los motivos por los que muchos programadores .Net tienen tan fuertes sentimientos en contra de WebForms. En este caso en particular, la practica imposibilidad de hacer tests me dice que este código va a ser difícil de cambiar y mantener.

Muchas de las mejores prácticas que escuchas por ahí, como YAGNI (you aren't going to need it; no lo vas a necesitar), bajo acople y alta cohesión, puede ser medido mediante la observación del código y pensando cómo lo testearías. Un método que hace demasiado, potencialmente está violando tanto YAGNI como la alta cohesión, y requerirá una cantidad dolorosa de código inicial en un test, y probablemente va a ser muy fácil de quebrar.

Hay un acrónimo  en la programación que se usa bastante: SOLID. Se refiere a cinco principios importantes del diseño orientado a objetos: Single responsibility principle (Principio de responsabilidad única), Open/close principle (Principio abierto/cerrado), Liskov substitution principle (Principio de substitución de Liskov), Interface segregation principle (Principio de segregación de interfaces) y Dependency inversion principle (Principio de inversión de dependencias). Estos son todos tópicos dignos de su propio capítulo, pero deberá bastar decir que muchos de ellos son algo ambiguos. ¿En qué momento un nuevo comportamiento o mejora es considerado una responsabilidad o en cuál se le asigna un componente? ¿Cuándo una interfaz se vuelve demasiado compleja? Estas son preguntas importantes y respuestas equivocadas van a tener consecuencias. La testabilidad y la experiencia son herramientas que puedes usar para resolver esta ambigüedad. (Un buen lugar para comenzar a aprender sobre SOLID es en la <a href="http://en.wikipedia.org/wiki/Solid_(object-oriented_design)">Wikipedia</a>.)

### Eficiencia: No tan simple como parece ###
Puede que aún no me creas sobre la testabilidad como métrica de calidad, pero confío en que crees que la calidad es un aspecto de suprema importancia. Otro de nuestros objetivos pragmáticos es la eficiencia, debido a que no debemos demorarnos mucho en producir un código de gran calidad. Uno esperaría que la eficiencia en cuanto a aprender y mejorar, fuera algo fácil de medir: puedo lograr XYZ ahora más rápido de lo que lo hacía antes, pero no es así.

Primero que nada, y lo más peligroso, es que los programadores no siempre nos damos cuenta de que hay mejores formas de hacer las cosas. Seamos honestos, muchos de los programadores rehúsa aceptar solo la posibilidad que exista. Es difícil para la gente, especialmente aquellos no muy apasionados sobre lo que hacen, el aceptar que hay mejores formas de hacer las cosas. No solo amenaza su comodidad, pero potencialmente sus carreras. Yo estaba en la escuela cuando Java iniciaba a ganar popularidad y quedé impresionado por lo cerrado de mente de los programadores que rehusaban aceptar que la recolección de basura automática, luego de corregir algunos menores problemas, podría ser algo muy útil (ni pensar en estándar). Ahora encuentro particularmente irónico ver programadores de Java reusando aceptar que los lenguajes dinámicos podrían convertirse en el nuevo Java (Especialmente dado que generalmente utilizan los mismos argumentos que los que usaban los programadores C++ contra Java)

Segundo, sin importar cuanto más eficiente es una tecnología o técnica, siempre serás más eficiente en lo que sabes versus lo que estás aprendiendo. Mi estrategia para sobrepasar esto es tomarme mi tiempo y reconocer que el proceso es una inversión de largo plazo. Además si eres astuto, probablemente puedas introducir algo de investigación en tu trabajo diario. Por astuto no quiero decir tramposo. Quiero decir que encuentres un proyecto secundario, no crítico. Aquel sistema de monitorización que querías hacer pero que nunca tuviste tiempo, o aquel prototipo que te solicitaron hacer. La aproximación exacta que tomes va a depender de tu forma de aprender. Todo lo que puedo decir es que no debieras esperar un incremento de productividad de la noche a la mañana.

### En Este Capítulo ###
Eso fue mucho texto y poco código. Este capítulo sentó las bases para los que continúan, los que presentarán mucho código y ejemplos. Definimos lo que significa calidad para nosotros asi como las métricas que usaremos para medirlo (testabilidad). Miramos a la eficiencia y descubrimos que mientras parecía fácil de medir, no lo era. Toma un respiro y considera algo del código que has escrito recientemente. Si hiciste tests, ¿Qué podría haber hecho los tests más simples y que tuvieran menor posibilidad de fallar si el sistema cambia? Si no lo hiciste, ¿Puedes imaginar algún inconveniente o problema que enfrentarías si decidieras hacer tests ahora?

## Capítulo 2 - Otra Introducción más a IoC ##
> "El propósito de la ingeniería de software es controlar la complejidad, no crearla." - Pamela Zave

Dependiendo de que tecnología uses, La Inversión de Control (IoC por sus siglas en inglés) y la Injección de Dependencias (DI por sus siglas en inglés) puede o no que sean algo en lo que pases leyendo o inviertas energía. En algunos lenguajes, IoC y DI juegan un rol explícito en el desarrollo. En otros, es casi invisible. Eso no significa que IoC es menos importante o fundamental en algunos lenguajes que en otros. Lo que es diferente es el mecanismo usado para lograr IoC, que es lo realmente facinante del asunto y es el porqué iremos a invertir un par de capítulos aprendiendo sobre esto.

Nuestro plan es iniciar con una corta introducción a IoC en este capítulo, luego examinaremos el problema de distintas perspectivas. El propósito no es etiquetar una aproximación como mejor que otra, sino que expandir como vemos y nos enfrentamos a un desafío central que constantemente encontramos al programar. Cuando finalmente pude ver IoC más allá del estrecho entendimiento mediante el cual fui introducido, un nuevo mundo se abrió a mis ojos.  No porque este sea un conocimento que sacuda la tierra - de hecho quizás nisiquiera cambie tu forma de programar. Lo que hizo por mi fue validar la importancia de expandir mi conocimiento más alla de mi zona de comodidad. Me mostró lo ignorante que era (y aun soy), y saber que eres ignorante es la clave para ser un programador exitoso.

### Unas palabras sobre Acoplamiento ##
Antes que iniciemos a examinar IoC, vamos a entender el problema que estamos tratando de solucionar. El acoplamiento es lo que obtienes cuando algo depende de otra cosa. Esa otra cosa puede ser una asignación, un método, una clase o incluso un sistema completo. Por ejemplo:

	#Incluso el código más simple nos pueda acoplar a otra clase o implementación:
	time = Time.now
	
	//...Algo un poco más complejo
	$('#logs').load('/orders/history', {id: _id});
	
	//...O algo mucho más grande
	var richList = Session.Query<Account>().Where(a => a.Amount > 10000000).List();


En cada uno de los ejemplos anteriores, nuestro código es dependiente de alguna otra implementación. Practicamente toda linea de código que escribas, tecnicamente  hablando, va a generar acoplamiento. Gran parte del tiempo el acoplamiento es benigno (Nadie sugiere que realices envolturas para cada librería o dependencia), sin embargo casos más complejos terminan fácilmente en problemas de testeabilidad, lo que indica que el código es difícil de modificar y mantener. El último ejemplo es más obvio, dado que es imposible hacer tests sin efectibamente llegar a la base de datos (aunque hablaremos de esto en futuros capítulos ya que ir a la base de datos en un test no es para nada una mala idea).

El tipo de acoplamiento fuerte que queremos evitar es el que introduce dependencias entre componentes o sistemas. Incluso cuando sabes que la implementación no va a cambiar, el acoplamiento hará difícil el refactoring y el mantenimiento.

### Bases de la Inversión de Control ###
Si el acoplamiento (que X sea dependiente de Y) es el problema, entonces la Inversión del control es la solución. IoC es un termino que engloba carias soluciones que nos ayudan a desacoplar, o cuando menos, reducir el acoplamiento. La idea general es cambiar el flujo procedural por algo en lo cual se tenga mayor control. Para mejor entender el concepto, veamos la forma más comun de IoC en .Net: Injección de Dependencias (DI).

El nombre *Injección de Dependencias* dice mucho de lo que la técnica permite: Injectar dependencias en nuestro código en vez de definirlas de manera estática (en duro). Estamos examinando primero esta forma de IoC no porque sea la más simple o sea la mejor, pero porque el resultado es particularmente explicíto y debido a que es una aproximación independiente del lenguaje, del framewor o la tecnología que estemos usando.

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

Este código tiene dos dependencias de las que haríamos bien de desacoplarnos. La primera es `SqlDataStore` y la otra `BCrypt`. La idea detrás de la Injección de Dependencias es tomar estas dos dependencias y administrarlas hacia nuetstra clase o método, en vez de tenerlas en duro. Esto puede ser logrado pasandolas como argumentos a nuestro método, estableciendo propiedades en nuestra clase, o mediante el método más común: entregarlas al constructor de la clase como argumentos. Cada aproximación tiene sus propais ventajas y desventajas, pero todas proveen el mismo beneficio: externalizan la dependencia y en un mondo de tipos estáticos, se puede programar contra interfaces. Aquí vemos el ejemplo anterior re-escrito con Injección de dependencia al nivel del constructor:

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


Nuestro código ahora nos escuda de la implementación directa, haciendo más facil mantener, cambiar y probar la funcionalidad. También, mientras algunos puedan encontrar que el método `FindByCredentials` ahora es un poco más dificil de entender (con lo que estoy de acuerdo), si realmente te pones a pensar, vas a encontrar que la clase `UserRepository` como un todo es más entendible. Puedes fácilmente mirar el costructor de `UserRepository` y entender *como* logra lo que hace. Otro beneficio, del cual hablaremos más adelante, es que la injección por constructor ayuda a mantener nuestras clases cohesivas (a tener un propósito acotado y bien definido) - ya que al tener muchas dependencias generalmente significa que la clase está haciendo demasiadas cosas.

Del ejemplo anterior debiera ser evidente cómo se verían las injecciones mediante propiedad o método. Injectar a un métod es útil solo cuando ese método tiene una dependencia específica (pero debiera ser usado de manera muy esporádica ya que un uso muy frecuente indica falta de cohesión entre la clase y los métodos). La injección mediante propiedades es ideal para dependencias opcionales (Que también son bastante raras). La injección mediante propiedad es también útil para el código interno de los frameworks, donde deseas que las clases que hereden no necesiten tener constructores muy complejos.

### Frameworks de Injección de Dependencias ###
En las comunidades donde DI es un patrón común, los frameworks de DI son abundantes y muy populares, por lo que haremos de esta mensión  algo breve. Lo que necesitas saber es que el ejemplo que presentamos previamente, cuando es hecho de manera manual, puede añadir una cantidad considerable de sobrecarga a nuestra programación. Si nuestro código desde la interfaz de usuario hasta los servicios externos (bases dedatos, servicios web, etc) tiene 4 o 5 niveles de profundidad y nuestras clases en promedio tienen 1 a 3 depndencias, entonces instanciar y rastrear nuestros objetos no va a ser muy divertido.

Es en enste pundo donde los frameworks de Injección de dependencia entran al juego. Los configuras con las dependencias que neceistas usar y luego dejas que el framework los administre y se preocupe de crear los objetos. Puedes pensar en ellos como en una super fábrica de objetos, que puede darse cuenta cuales son los servicios que una clase necesita y se los administra de manera automática, para entregarte una clase y todo su árbol de dependencias creado y listo para usar. 

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

El framework DI verá que le solicitamos un ´IUserRepository´, entonces revisa en su configuración que necesita entregar un `UserRepository`. En ese momento, revisa el constructor y entiende que tiene dos dependencias. Nuevamente revisa su configuración y encuentra estas dependencias, así que las crea y las injecta, y de esta forma es capaz de entregarnos una instancia lista para usar.

Mantén en mente que el objetivo de un framework DI no es hacer el código dinamicamente enlazable. Queremos ser capaces de programar contra interfaces injectadas donde sea necesario. Es algo que podemos hacer de manera manual, pero incluso ejemplos simples son un verdadero dolor. Un framework DI automatiza una pequela pero importante parte del proceso (Creación de objetos con dependencias).

Es difícil dejar pasar la oportunidad para quejarce por las configuraciones basadas en XML, asi que... La mayoría de los frameworks de DI en .Net proveen tanto configuraciones por código (como la que vimos arriba) como configuraciones mediante XML. El beneficio de usar configuraciones por código es que tienes la capacidad de refactorizar y testear tus configuraciones. No hay ninguna ventaja con configuraciones en XML, aunque algunos programadores argumentarán que con XML no necesitan recompilar para cambiar una dependencia. Yo digo que esos es basura: Un cambio en una configuración de dependencia, independiente de donde se almacene, amerita el mismo proceso de QA y publicación que cualquier otro cambio en la aplicación.

### Anti patron de Injección de Dependencias ###
Finalizar nuestra introducción a Injección de dependencias con lo que hemos cubierto hasta ahora sería desfavorable. Hemos cubierto las mecánicas de DI y los frameworks de DI, pero al enfocarnos en el *que* hemos introducido algunos feos *como*. Nuestra instancia de  `kernel` del ejemplo anterior es thread-safe, y podríamos crear una clase estática y llamarla algo como `Factory.Get<T>` en todas partes de nuestro código. Como sugerimos arriba, los frameworks de DI pueden verse como una suplantación de el keyword `new`, así que podría ser una buena aproximación. 
	

Usar nuestro framework de DI de esta forma es conocido como el patrón Service Locator, pero es generalmente percibido como un anti-patrón. Uno necesita limitar el uso directo del framework DI. Si estás usando un framework moderno, debieran haber puntos en los cuales puedas introducir la resolución de dependencias mediante el framework DI. Por ejemplo. ASP.NET MVC 1 y 2 permiten que proveas un controller factory personalizado, que puede ser usado como punto de inicio para la resolución de dependencias (La versión 3 tiene un modelo aun más simple) De hecho, la mayoría de los frameworks DI proveerán estas extensiones para diversos Frameworks, como es el caso del `NinjectHttpApplication` de ninject,  del cual simplemente heredas y le configuras los modelos y listo. Como un check simple, revisa cuantas veces estás importanto el namespace de tu framework DI. No debieras encontrarlo en más de 4 o 5 lugares.
El punto es que con lenguajes de tipos estáticos, los frameworks de DI debieran ser un ejercicio solo de configuración que de programación. Puede que te encuentres llamando al kernell de manera directa en las partes más bajas de tu código, pero la resolución de dependencias automática debiera encargarse de ese punto en adelante. Si tu framework de DI no permite realizar esto, cambia el framework por uno más potente.

### En este Capítulo ###
En este capítulo hemos visto que es Inversión de Control y el problema que estamos tratando de solucionar con esto (reducción de acoplamiento). También vimos un patrón comun de IoC: la Injección de dependencia. Para muchos programadores esta es una forma diferente de programar y pensar. En todo caso, recuerden que ganamos mucho de esto: El código es más fácil de cambiar y refactorizar, clases con baja cohesión son fáciles de descubrir y los tests son más faciles de hacer.

## Chapter 3 - IoC 180&deg; ##
> "If you do not raise your eyes you will think that you are the highest point" - Antonio Porchia

When you first learn about IoC and start playing with a DI framework, you don't think to yourself *I wonder how else I could resolve dependencies?* Why would you? DI is straightforward as well as being a good fit with how most people organize their Java or .NET code. No one would blame you for thinking, like I did, that this is how everyone does it. It isn't. DI is a pattern suited for object-oriented programming with static languages. Switch to a different paradigm and you'll find different solutions.

### Dynamic Mind Shift ###
It's common for developers to think of dynamic languages and dynamic typing as synonyms. It's true that most (though not all) dynamic languages are dynamically typed. The fact though is that dynamic languages execute many things at runtime, which static languages do at compile time. The implication is that, within a dynamic runtime, developers have greater capabilities at runtime than their static counterparts.

At first such power might seem to be of limited use. After all, how often do you need to change your code at runtime? As is often the case, we don't know we need something until it's made available to us.  Then we wonder how we ever lived without it. Think of it in terms of the features that have been added to C# over the years: generics, anonymous methods and LINQ (to name a few). A dynamic runtime is the same, the impact is difficult to grasp as long as the way you think is constrained by your experience with static languages. Reflection isn't an integral part of your work because it's both limited and cumbersome; yet make it powerful and simple and it might be a tool you leverage on a daily basis. (To be honest, comparing dynamic languages with reflection is hugely unjust to dynamic languages, we're just trying to draw some initial parallels.)

What does this have to do with Inversion of Control? The flexible nature of dynamic languages means that IoC is built directly into most dynamic languages. There's no need to inject parameters or use a framework, simply leverage the language's capabilities. Let's look at an example:

	class User
	  def self.find_user(username, password)
	    user = first(:conditions => {:username => username})
	    user.nil? || !Encryptor.password_match(user, password) ? nil : user
	  end
	end

Our code has two dependencies: `first` will access an underlying store (which may not be obvious if you aren't familiar with Ruby) and `Encryptor` is a made-up class responsible for matching a user's hashed password with a supplied password. In a static world both of these would be troublesome. In Ruby, and other dynamic languages? Simply change what `first` and `Encryptor` do:

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

Keep an open mind and remember that this code may be as mysterious to you as anonymous methods and lambdas are to someone else. We'll discuss the code in further detail, but let's first look at how it might be used:

	it "returns the found user" do
	  user = User.new
	  first_returns(user)
	  password_match_returns(true)
	  User.find_user('leto', 'ghanima').should == user
	end

In real life you'd use a mocking framework to take care of this and provide a cleaner syntax and more powerful features. But, putting aside some of the magic, we can see that our two methods redefine the `:first` and `password_match` methods at runtime so that they implement a behavior that our test can use. To really start understanding this, we need to cover singleton classes.

#### Singleton and Metaclasses ####

In C#, Java and most other static languages a class can safely be thought of as a rigid template. You define fields and methods and compile your code using classes as an immutable contract. Classes serve a very useful purpose as a design-time tool. The problem with classes, by no fault of their own, is that most programmers think classes and object-oriented programming are one and the same. They aren't. Object orientated programming is, as the name implies, about the living objects of your running code. In a static language this means instances. Since instances are tightly bound to the template defined by their respective class, it's easy to see why developers mix the two concepts.

Look beyond static languages though and you'll see a different story. Not only is there no law that says  classes cannot themselves be living things, but object-oriented programming can happily exist without classes. The best example that you're probably already familiar would be from JavaScript. Behold, OOP without classes:

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

As always, the point isn't that one approach is better than another, but rather to gain a different perspective - likely, in this case, on knowledge you already possess. Doing a decade of object-oriented programming a certain way is the kind of experience that can compromise your ability to grow.

So object-oriented doesn't *require* classes, but as templates, classes are quite handy. This is where Ruby and singleton classes come in; because, as we've already mentioned, there's no law that says a class has to be a predefined and unchangeable template.

In Ruby every object has its own class, called a singleton class. This lets you define members on specific instances, like:

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

Technically, we aren't adding the `is_over_9000?` method to the `goku` object, we are adding it to its invisible singleton class, which `goku` inherits from and thus has access to. We call the singleton class invisible because both `goku.class` and `vegeta.class` will return `Sayan`. There are ways to expose a singleton class, but when you aren't doing metaprogramming, singleton classes are transparent.

To get access to a singleton class, which is itself a real object, we use the `class << ` syntax. For example the `is_over_9000?` method could alternatively be defined like so:
	
	class << goku
		def is_over_9000?
			true
		end
	end

If we want to assign the singleton class to a variable, we can simply expose `self`:

	singleton = class << goku
		self
	end
	
	#or, more common and concisely, using ; instead of newlines
	singleton = class << goku; self; end

Interestingly (and I'm not too sure why I find it interesting), if we look at the `goku` and `singleton` instances, we get the following output:

	goku
	=> #<Sayan:0x10053a1f0>
	singleton
	=> #<Class:#<Sayan:0x10053a1f0>>

In Ruby, everything is an object. Even a class is an object (which inherits from `Class`, which in turn inherits from `Object`). That means you can invoke methods on your classes:

	Sayan.is_a?(Object)
	=> true
	Sayan.is_a?(Integer)
	=> false
	Sayan.to_s
	=> "Sayan"

Since classes are objects, they too have singleton classes (which are often called metaclasses). We can get access to a class' metaclass via the same `class <<` syntax we used for an instance:

	metaclass = class << Sayan
		self
	end
	#or, the more consice approach
	metaclass = class << Sayan; self; end

Singleton classes aren't really something you'll deal with too often, but metaclasses are important because class methods are defined in the metaclasses. Class methods are, in a lot of ways, like static methods in C# or Java. They are defined one of two ways and used like you'd expect:

	
	class Sayan
		# First way to define a class method, use self.methodName
		def self.find_most_powerful()
		  # todo
		end
		
		#second method, opening the metaclass
		class << self
			def all_by_level(superSayanLevel)
				# todo
			end
		end
	end
	
	powerfulSayans = Sayan.all_by_level(3)

(Understanding `self` in Ruby, specifically what `self` refers to in a given context, is important to mastering the language.)

The key difference though, between Ruby class methods and Java/C# static methods, is that class methods are defined against a metaclass which is an object. In other words, while class methods resemble static methods, they actually share more in common with instance methods.

What does all this get us? Much of the rigidity you'll bump up against in a static language doesn't exist in a dynamic language. Sealed classes, non virtual methods and static methods, which are mechanisms to stop you from doing something, vanish. There are pros and cons to both approaches, but there's no reason not to be familiar with both. 

I do want to point out that, from a testability perspective, metaprogramming does have significant advantages - the difficulty in testing a static `password_match` method in C# should be proof enough of that. We can't simply overwrite the implementation, as we did at the start of this chapter in Ruby, because classes aren't objects. DI, or even interfaces, simply aren't necessary in Ruby. The decoupling you achieve in C# via injecting interfaces and managing dependencies is replaced by the very nature of the Ruby language. 

### Events/Callbacks ###
Another way to reduce coupling is to leverage events and callbacks. It's been long understood that events, by their very nature, provide protection against coupling. Code which raises an event is saying *I don't care who you are or what you are going to do, but it's time to do it.* There could be 0 listeners, or a hundred, they could do all sorts of unrelated things, but none of that matters to the calling code. The code ends up easy to test because, from the caller's point of view, you just need to verify that the event is raised and from the callee's point of view that they register for the event.

The reason we don't use events everywhere is because they just don't lend themselves to the linear flow we use for most code. However, over the last couple years, this has started to change. Why? The resurgence of JavaScript. We now have more code written in JavaScript and more developers are letting go of their old (generally negative) perceptions and learning the language anew. JavaScript is no longer a place where we can rely on hacks and hope it all keeps working. There's been a shift towards quality and maintainable JavaScript. That means we need to start worrying about coupling, cohesion and testability. When it comes to that, events are to JavaScript what DI is to Java/C# or metaprogramming is to Ruby.

Let's say you're a [jQuery](http://www.jquery.com/) master (if you aren't, you can jump to Appendix A then B to start that journey whenever you want) and have built a series of generic plugins. These are things that we plan on reusing throughout our site. A lot of these plugins will need to interact with each other. For example, one of the plugins turns a simple list of rows into a pageable and sortable grid, and another allows a form to be submitted via AJAX. Of course, when the user submits a new record, via the AJAX form, the fancy grid needs to be updated. First, let's look at the basic setup:

	//applies the fancyGrid plugin to the element with an id of users
	$('#users').fancyGrid();
	
	//applies the fancySubmit plugin to the element with an id of add_user
	$('#add_user').fancySubmit();

The core of our `fancySubmit` plugin will be something as simple as:

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

(If you aren't familiar with jQuery, this code is intercepting our form's `submit` event in order to submit the data via AJAX. The response from that AJAX call is then handled by the `handleResponse` function. Again, you might want to skip to Appendix A and B to get up to speed on jQuery.)

`handleResponse` can handle generic cases (errors, validation) directly, but anything more specific will depend on the specific context it's being used in. The solution? Allow a callback to be passed into the plugin and trigger it when appropriate:

	handleResponse: function(r){
		//add some generic handling here first, maybe
		if (options.onSubmit != null) { options.onSubmit(r); }
	}

With that simple change, we can now tie the two plugins together, without really having to tie them together:

	//applies the fancyGrid plugin to the element with an id of users
	var $users = $('#users').fancyGrid();
	
	//applies the fancySubmit plugin to the element with an id of add_user
	$('#add_user').fancySubmit({
		onSubmit: function(r) { $users.fancyGrid('newRow', r); }
	});

Using this approach, the two plugins work together without knowing anything about each other. This helps ensure that your code stays highly reusable and cohesive.

### Testing It ###
We can test `handleResponse` by supplying a fake callback which can make some basic assertions. However, we have to deal with call to `$.post`. Since JavaScript is dynamic like Ruby, it too provides a mechanism to change our runtime definitions. Combining our dynamic rewrite with our custom callbacks yields:

	test("executes the onSubmit callback after receiving a response", function()
	{
		expect(1); //ignore this for now
		
		//overwrite the $.post method to always execute the callback with a canned response
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

Ignore the call to `expect` for now, we'll get to it in a minute. We rewrite the `$.post` function, circumventing the heavy implementation with something controllable and lightweight. `$.post` now essentially executes the 3rd parameter (which if we look back up at the plugin is a call to `self.handleResponse`) with a hardcoded parameters. Next, we initialize the plugin with our callback, which will assert that the supplied parameter is what we expect. Finally, we actually submit the form to execute the actual code.

About the call to `expect`, this tells our testing framework, [Qunit](http://docs.jquery.com/Qunit) in this case, that 1 expectation should be called. This is key when dealing with callbacks and events. What would happen if we didn't call `expect` and also changed our plugin to not invoke our callback? Our test would still pass because nothing would ever be asserted. By specifying `expect(1)` we ensure that our real expectation (that our callback is called, and called with the correct parameters) is invoked - if `ok` isn't called, then `expect` will fail and we'll know something isn't right.

The introduction of anonymous methods and lambdas make similar code possible, and even preferable in some situations, in C#.

### In This Chapter ###
Depending on your experience with Ruby and jQuery, this chapter might have been overwhelming. We covered some advanced techniques in languages less familiar to us. We possibly picked the most complicated part of Ruby to look at (metaprogramming), so don't be discouraged if you missed some, or even most of it. We also saw some pretty different testing scenarios. Most important though, was how we were able to relearn something we thought we knew well (IoC) by learning what, to others, is pretty fundamental stuff. You can almost consider IoC a built-in feature of Ruby, much like you'd see LINQ as a built-in feature of C#. Even if you don't understand the nuance of the code or the implications it has on day to day programming, this chapter should still showcase the value of learning and growing.

## Chapter 4 - Testing ##
 > "Quality is not an act, it is a habit" - Aristotle

So far we've framed the discussion around the idea of testability as a quality metric. Now it's time to look at writing actual tests. There are a number of benefits to writing tests. The most important, in my opinion, is the impact on code quality. I'd easily argue that writing tests is a design exercise since it helps flush out a bunch of anti-patterns that make your code unsustainable. Beyond that, writing tests  helps ensure that your code does what it's supposed to do, and acts as an important safety net when you make changes.

I won't lie to you. Writing effective tests isn't something that happens overnight. It's a long-term investment that'll benefit both your code and you. It can be a pain, both as you get started and even when you are experienced. It will slow you down at first, but even on your first attempt the benefits should outweigh the costs. Remember though, you don't have to test everything. Start with the most critical parts of your system. As a developer, being effective at unit testing should be one of the skills you excel at. Start today, take the hit in productivity and learn. Learning to write effective tests is, hands down, the single most important piece of advice I could give an aspiring developer.

### Testing Basics ###
Before we can look at testing best practices, we need to lay down a basic foundation. If this is a newish topic for you, you might have noticed a lot of acronyms, competing ideas and approaches. My own experience says that if you start writing tests today you'll steadily progress to writing effective tests. The journey from learning to mastering is a critical learning process, which you couldn't avoid if you wanted to (regardless of a fancy acronym someone gave a phase). For the rest of this chapter we'll talk about **unit tests**. Unit tests assert the most atomic aspects of your system, be it technical details or behavioral expectations. Unit tests leverage a testing framework. Our C# examples will use [NUnit](http://www.nunit.org/), our Ruby examples will use [RSpec](http://rspec.info/) and our JavaScript will use [QUnit](http://docs.jquery.com/Qunit). Let's look at our first example:

	#ruby
	class User
		def self.passwordIsValid(password, confirmation)
			return false if password.nil? || password != confirmation
	
			return password.length >= 8
		end
	end	

(To follow general Ruby guidelines, the above method should probably be named `password_valid?`. However, the trailing question mark was omitted to make the following tests valid in C# and JavaScript - which don't look so kindly on question marks appearing in method names.)

When I look at the above method, which validates that a password is 8 or more characters long and matches a confirmation, I see the opportunity for 4 tests:

	[Test] //C#
	public void PasswordIsInvalidWhenBlank() 
	{
		Assert.IsFalse(User.passwordIsValid(null, "confirmation"), "Password cannot be false");
	}
	
	//javascript
	test("Password is invalid when it doesn't match the confirmation", function(){
		equals(User.passwordIsValid("password", "confirmation"), false, "Password must match the confirmation")
	});
	
	#ruby
	it "Should validate a minimum length" do
		User.passwordIsValid("1234567", "1234567").should == false
	end
	
	[Test] //C#
	public void PasswordIsValidWhenItMatchesTheConfirmationAndMeetsTheMinimumLength()
	{
		Assert.IsTrue(User.passwordIsValid("12345678", "12345678"));
		Assert.IsTrue(User.passwordIsValid("a long password should also work!", "a long password should also work!"));
	}

While the syntax differs, and the available assertion methods will vary, at their core, the libraries are quite similar as is the testing methodology. We started with a trivial example because that's always the right place to start; why burden ourselves with complex examples when all we are trying to do is find our bearings?

There is a point to the above example, besides showing the basic syntax of testing. The point is to help define what a *unit* is when talking about testing. It isn't simply a method, but rather the behaviors that make up a method. Our simple `passwordIsValid` has some technical details which need to be tested (handling a nil/null password) as well as behavior details (what happens when it's too short or doesn't match the confirmation). When talking about testability, we are basically talking about how easy each of these units is to test. The above code is simple and consequently easy to test.

### Mocks and Stubs ###
Let's take a step back from the stubs and mocks we wrote for Ruby and JavaScript back in Chapter 3 and build our knowledge from the ground up. I've read a handful of explanations on *Mocks vs Stubs* and to me it still isn't very clear. I see the two as being similar, with mocks being smarter and mostly about asserting expectations as opposed to stubs which are dumb and used to just get code executing properly. As we write more tests the distinction will hopefully become clearer. For now, let's go back to an example we introduced a few chapters back:

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

When we look at the units that make up `FindByCredentials`, we see that:

1. The underlying store is used to find the actual user
2. Null is returned if the store didn't find a user
3. Null is returned if the stored password doesn't match the supplied password
4. The user is returned if the username and password are valid

A common way to test a method with these types of dependencies is to leverage the dependency injection we added to our class and inject mock objects. In the following chapter we'll talk about an alternative approach to mock-heavy code, but making generous use of mock objects is a good place to start your testing journey (especially since it's something that will always be the best approach in many circumstances regardless of what you generally prefer).

We could, if we were truly stubborn, write our own mock objects:

	public class FakeDataStore : IDataStore
	{
		public User OnNextCallReturn{get;set;}
		public User FindOneByNamedQuery(string name, object parameters)
		{
			return OnNextCallReturn;
		}
	}

Which we could then use in a test, like:

	[Test]
	public void ReturnsNullIfTheUserIsntFoundInTheStore() 
	{
		var store = new FakeDataStore{OnNextCallReturn = null};
		var repository = new UserRepository(store, null);
		Assert.IsNull(repository.FindByCredentials("username", "password"));
	}

It's an interesting example to look at because of how explicit it is with respect to injecting a different and fake dependency, but even in a simple system it's an unsustainable approach and one which waters down the value of our tests. The solution is to use a mocking framework.

### Mocking Frameworks ###
Mocking frameworks are powerful tools in your testing arsenal. Admittedly, they can be a little tricky to  get used to so we'll try to go over them at a reasonable pace. The purpose behind mocking frameworks is to, in a manner of speaking, automate the creation of our `FakeDataStore` above as well as enhance how our tests interact with it.  We'll look at an example and work backwards from there. Using a mocking framework, our above test could be rewritten, without the need for our `FakeDataStore`:

	[Test] //using FakeItEasy in C#
	public void ReturnsNullIfTheUserIsntFoundInTheStore() 
	{
		var store = A.Fake<IDataStore>();
		A.CallTo(() => store.FindOneByNamedQuery("FindUserByUserName", new {username = "theUserName"})).Returns(null);
		var repository = new UserRepository(store, null);
		Assert.IsNull(repository.FindByCredentials("theUserName", "password"));
	}
	
	#using rspec in Ruby
	it "returns nil if the user isn't found in the store" do
		User.shoud_receive(:find_by_username).with('theUserName').and_return(nil)
		User.find_by_credentials('theUserName', 'password').should be_nils
	end

(The Ruby version is different to account for differences in how the implementation would likely be written, but the idea behind setting up the mock (`User.should_receive...`) is what's important in this example).

What the above code does (and both the C# and Ruby versions do the same thing), is define an expectation with specific parameters and a return value. 

In chapter 3 we saw how this can be achieved in Ruby. A mocking framework, in this case [rspec](http://rspec.info/), can dynamically add the `should_receive` method to the `User` object to make it do whatever it wants. It can actually go a step further and add the `should_receive` method to any object, thus making everything mockable. With this code in place, it isn't a huge leap to record specific parameter expectation and return values.

Depending on how comfortable you are with proxies (more specifically dynamic proxies), the C# implementation may or may not be as straightforward. Since we can't dynamically change the meaning of a method, we rely on injecting interfaces. Interfaces are rigid things. What C# (and Java) mocking libraries do is create a proxy based on an interface. Think of a proxy as an in-memory implementation of the interface. This is what our call to `new Mock<IDataStore>();` does. However, this instance of an `IDataStore` is extremely dumb - call any method on it, and you'll get an exception (you don't expect this magically wired up instance to know how to actually find a user by username do you?) What it does let us do is define expectations and return values. We see this in action when we use the `A.CallTo` method.
	
If you are able to wrap your mind around the idea of a temporary, in-memory and quite incomplete implementation of the `IDataStore`, then you're on your way to understanding mocking. If it still isn't clear, you should play with some examples. Create mock objects, invoke methods which you haven't setup expectations for or invoke methods using different parameters. The .NET mocking framework being used is [FakeItEasy](http://code.google.com/p/fakeiteasy/). It's relatively new to me, but I enjoy the explicitness of its syntax as well as some of the stubbing features. There are many open source mocking and unit testing frameworks available, use whichever one suits you best.

Most mocking frameworks are actually quite powerful. The above examples are the most common cases, but don't let that fool you. With a good mocking framework it's possible to be as strict or as loose as you want. You can, for example, ignore arguments or not care whether particular methods are or aren't called. Or, you can specify ordering and use complex parameter matchers. In the next chapter we'll talk more about these different approaches to mocking and testing. 

### In This Chapter ###
This chapter focused on the basics of unit testing and mocking. One of the most important things we discussed was exactly what a unit test is. Essentially, we saw how one simple method had four distinct behavior, each a good candidate for an individual test. We also looked at mocking, which is both a powerful and complicated tool. If it still isn't clear, maybe because of the somewhat odd syntax, go back and look at the manual approach that we took. It's more important to understand the concept of mocking in general than the implementation of the mocking frameworks. That said, understanding proxying in a static language is an important concept; you'll run into it everywhere and probably even want to take advantage of it yourself.