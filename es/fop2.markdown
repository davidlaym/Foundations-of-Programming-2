# Fundamentos de Programaci�n 2 #
> "Si al principio no resulta, intenta, intenta, intenta otra vez" - William E. Hickson

## Licencia ##
Fundamentos de Programaci�n 2 est� bajo la licencia Attribution-NonCommercial 3.0 Unported. **Este libro no le debiera haber costado dinero**

Eres libre de copiar, distribuir, modificar y/o compartir el libro. Sin embargo, solicito que siempre atribuyas este libro a m�, Karl Seguin, y que no lo uses para prop�sitos comerciales.

Puedes ver el texto completo de la licencia en:
<http://creativecommons.org/licenses/by-nc/3.0/es/legalcode.es>

## �ltima Revisi�n ##
Este libro est� actualmente en desarrollo, el lanzamiento final est� esperado para inicios de Febrero de 2011

Para obtener la �ltima versi�n, visita <http://github.com/karlseguin/foundations2>.

## Acerca del Autor ##
Karl Seguin es un desarrollador con experiencias en varios campos y tecnolog�as. Es un experto desarrollador en .Net y aprendiendo Ruby. Es familiar con todos los aspectos de el desarrollo web, concurrencia y programaci�n de Sockets y varias tecnolog�as SQL y NOSQL. Es un contribuyente semi-activo de proyectos de c�digo abierto, escritor t�cnico y un exponente espor�dico.

Su blog puede ser accedido desde <http://openmymind.net>, y sus tweets via [@karlseguin](http://twitter.com/karlseguin)

El es tambi�n el fundador de servicios gratuitos para desarrolladores de juegos en <http://mogade.com>.

## Introducci�n ##
Siempre me encuentro sorprendido por el n�mero de programadores con los que me encuentro. Mucho de sus vidas lo dedican al trabajo del cual somos afortunados por tener la oportunidad de estar haciendo lo que amamos. Esta no es una propiedad �nica de los programadores, pero es lo suficientemente extra�a para que la mayor�a de la gente lo encuentre sorprendente. "�Vas a casa y *trabajas* cada d�a?" nos preguntan. Solo nuestros m�s cercanos amigos y colegas apasionados entienden que *trabajo* tiene dos significados para nosotros, ninguno de los que es una esclavitud de 9 a 5.

Probablemente has notado que el entusiasmo y puje es una caracter�stica critica en un campo tan joven. La tecnolog�a contin�a cambiando a un paso acelerado, el campo est� creciendo y los sistemas est�n cada d�a volvi�ndose m�s complejos. El resultado es una clara divisi�n entre programadores que aman su oficio y lo que no. Estas o bien leyendo, intentando y a veces fallando, o est�s estancado en el pasado, probablemente ignorante de lo atr�s que te has quedado.

Desafortunadamente, ser apasionado por lo que haces no siempre es suficiente. Todos tenemos distintas fortalezas y debilidades, diferentes formas de aprender y diferentes tolerancias al fallo. Tambi�n tenemos el constante flujo de nuevas tecnolog�as que hacen dif�cil decidir en cual ocupar el tiempo para aprender. La verdad es que no soy un gran programador. Soy un buen programador que le gusta aprender (y ense�ar) y que disfruta jugando con la tecnolog�a. He visto personas aprender un lenguaje solo d�as cuando a mi me ha costado meses, o escribir algoritmos con los cuales pretendo estar de acuerdo porque simplemente no pude entenderlo. Las Fundaciones de la Programaci�n es una serie pensada para ayudar a la gente como yo, gente a la que le interesa lo que hacen y lo queren hacer mejor, pero no est�n seguros como hacerlo.

Espero que este libro te ayude.

### Respecto al Original ###
El libro original [Foundations of Programming](https://github.com/karlseguin/Foundations-of-Programming-Ebook) ha sido, bajo mis est�ndares, un �xito. Tal parece haber ayudado genuinamente a desarrolladores y servido a una real necesidad cada libro, el original y este, existen por separado. Son independientes el uno del otro. Sin embargo podr�a sugerir que si tienes en mente leer el original, lo hagas antes de continuar con este. Mis vistas han madurado y en algunos casos cambiado o clarificado. Creo que mucho puede ser obtenido en ver c�mo he evolucionado en la programaci�n.

## Cap�tulo 1 - Calidad y Eficiencia ##
>"La calidad nunca es un accidente, siempre es resultado de un esfuerzo inteligente" - John Ruskin

Pragm�ticamente, la raz�n por la que yo y (asumo) la mayor�a de los programadores, estamos deseosos de aprender, es para mejorar la calidad del c�digo que escribimos al igual que nuestra eficiencia. No conozco programador que ocupe tiempo aprendiendo nuevos acercamientos y tecnolog�as  con el objetivo expl�cito de escribir peor c�digo, o encontrar medios para trabajar m�s lento. Pero, �C�mo medimos la eficiencia y la calidad? �Qu� cosa, como creadores, consideramos que son nuestros objetivos?

Aquellos del tipo administrativo, considerar�an como medida de calidad puramente la satisfacci�n del cliente. Aun cuando es ciertamente importante, los buenos programadores son los interesados con mayores expectativas y tambi�n son los m�s cr�ticos. Como DeMarco y Lister dijeron en Peopleware, **Todos tendemos a vincular fuertemente nuestra auto estima con la calidad del producto que producimos - no con la cantidad del producto, sino con la calidad.** Encuentro dif�cil poder expresar con palabras, desde la perspectiva de un programador, lo que significa la calidad; pero, estoy seguro que no solo muchos de nosotros coincidimos en la definici�n, sino que tambi�n podemos reconocerla f�cilmente (o la falta de ella). Calidad es sobre encontrar una soluci�n elegante para un problema - tanto a un nivel micro (comportamientos individuales) como macro (el sistema como un todo). �Qu� es *elegante* entonces? Var�a seg�n el contexto del problema pero, generalmente, una soluci�n elegante es tanto la m�s simple posible, como la m�s expl�cita y f�cil de entender.

Mientras m�s programo, m�s me doy cuenta de algo realmente sorprendente. No solo la soluci�n m�s sencilla es obviamente la m�s f�cil de implementar, sino que tambi�n la m�s f�cil de entender, mantener y cambiar. Las soluciones simples tambi�n tienden a tener mejor rendimiento que aproximaciones m�s complejas. Esto es particularmente sorprendente cuando te encuentras hasta las rodillas en un l�o sobre trabajado en donde la intenci�n original de flexibilidad, rendimiento y eficiencia son saboteadas por complejidad artificial. Esto no significa que est� a favor de la programaci�n sin consideraci�n por el dise�o. En vez, creo que dada cierta experiencia y reflexi�n, un balance entre pensar por delante los problemas y el pragmatismo no solo es lograble, sino que tambi�n bastante natural.

Me gustar�a decirte cu�l es la respuesta. No es que no lo sepa. El problema es que tengo que anteponer una advertencia; sino corro el riesgo que me des un desprecio y dejes el libro aqu�. Yo s� que muchos de ustedes est� cansados de escucharlo, pero les suplico que me escuchen y reconozcan que probablemente no estoy diciendo lo que ustedes piensan que digo. �Ok? Entonces, el secreto para escribir c�digo con calidad es asegurarse de que el c�digo es testeable. ESPERA... no te vayas aun. No estoy diciendo que debas testear tu c�digo (Ciertamente tampoco niego que se deba hacer) solo estoy diciendo que si, te�ricamente, fueras a testear tu c�digo, no debiera ser dif�cil. El c�digo puede ser testeable sin efectivamente testearlo y al final, es a lo que debieras apuntar.

Por un largo tiempo pensaba que la soluci�n era realmente as� de simple. Escribir tests y la calidad del c�digo ir�a incrementando. Pero m�s recientemente me he dado cuenta que no todos los tests son creados iguales y que es enteramente posible, si es que no com�n, tener realmente malos tests. Entender qu� es lo que hace a un tests bueno, y por lo tanto qu� es lo que hace al c�digo testeable, viene con la experiencia y espero, junto con los siguientes cap�tulos, pueda ayudarte a esquivar algunas de las piedras que me he encontrado en el camino. Es por esto que mucho de este libro estar� dedicado tanto a escribir tests como a la testeabilidad del c�digo. No mezcles testabilidad como una metrica con escribir tests. Es como escribir un mont�n de c�digo mantenible que no necesita mantenimiento. Es un objetivo, no una actividad. Ahora, es cierto que la mejor manera de descubrir que una soluci�n es testeable es mediante la escritura de un test. Eso s�, espero poder convencerte de que le des un intento; en los �ltimos tres a�os el convertirme en un escritor de tests efectivo es una de las cosas que m�s me ha ayudado a elevar mi habilidad. Sin embargo, es enteramente posible ver un m�todo o un sistema y estimar su testeabilidad, y por lo tanto, su calidad, sin escribir un test.

### Testeabilidad como una medida de calidad ###
No te culpo si eres esc�ptico. Todo lo que puedo hacer es prometer que mientras puede se que gastemos algo de tiempo escribiendo tests, no voy a tratar de hacerte sentir que est�s haciendo algo malo si elijes no hacer tests. Tambi�n, puedo mostrarte un ejemplo sencillo de lo que quiero decir:

	//Un ejemplo de c�digo dificil de probar, y por lo tanto, de mala calidad.
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
(Si esta fuera una peque�a aplicaci�n desechable, podr�amos perdonarla. Aunque tambi�n debo decir que en mi experiencia, programadores h�biles escriben c�digo limpio sin importar la expectativa de vida para el c�digo. Esto es probablemente por el hecho que todos conocemos c�digo de *prototipos* que ha terminado con un periodo de vida vergonzosamente largo.)
 
Este trozo de c�digo est� lejos de la perfecci�n. Si espec�ficamente lo miramos desde una perspectiva de la testabilidad, podemos ver una cantidad de dependencias que lo har�n dif�cil de testear, como por ejemplo `SqlServerDataStore.FindUser` y `Response.Redirect`, por nombrar algunas. Lamentablemente muchas de estas vienen incluidas en el framework, lo que es uno de los motivos por los que muchos programadores .Net tienen tan fuertes sentimientos en contra de WebForms. En este caso en particular, la practica imposibilidad de hacer tests me dice que este c�digo va a ser dif�cil de cambiar y mantener.

Muchas de las mejores pr�cticas que escuchas por ah�, como YAGNI (you aren't going to need it; no lo vas a necesitar), bajo acople y alta cohesi�n, puede ser medido mediante la observaci�n del c�digo y pensando c�mo lo testear�as. Un m�todo que hace demasiado, potencialmente est� violando tanto YAGNI como la alta cohesi�n, y requerir� una cantidad dolorosa de c�digo inicial en un test, y probablemente va a ser muy f�cil de quebrar.

Hay un acr�nimo  en la programaci�n que se usa bastante: SOLID. Se refiere a cinco principios importantes del dise�o orientado a objetos: Single responsibility principle (Principio de responsabilidad �nica), Open/close principle (Principio abierto/cerrado), Liskov substitution principle (Principio de substituci�n de Liskov), Interface segregation principle (Principio de segregaci�n de interfaces) y Dependency inversion principle (Principio de inversi�n de dependencias). Estos son todos t�picos dignos de su propio cap�tulo, pero deber� bastar decir que muchos de ellos son algo ambiguos. �En qu� momento un nuevo comportamiento o mejora es considerado una responsabilidad o en cu�l se le asigna un componente? �Cu�ndo una interfaz se vuelve demasiado compleja? Estas son preguntas importantes y respuestas equivocadas van a tener consecuencias. La testabilidad y la experiencia son herramientas que puedes usar para resolver esta ambig�edad. (Un buen lugar para comenzar a aprender sobre SOLID es en la <a href="http://en.wikipedia.org/wiki/Solid_(object-oriented_design)">Wikipedia</a>.)

### Eficiencia: No tan simple como parece ###
Puede que a�n no me creas sobre la testabilidad como m�trica de calidad, pero conf�o en que crees que la calidad es un aspecto de suprema importancia. Otro de nuestros objetivos pragm�ticos es la eficiencia, debido a que no debemos demorarnos mucho en producir un c�digo de gran calidad. Uno esperar�a que la eficiencia en cuanto a aprender y mejorar, fuera algo f�cil de medir: puedo lograr XYZ ahora m�s r�pido de lo que lo hac�a antes, pero no es as�.

Primero que nada, y lo m�s peligroso, es que los programadores no siempre nos damos cuenta de que hay mejores formas de hacer las cosas. Seamos honestos, muchos de los programadores reh�sa aceptar solo la posibilidad que exista. Es dif�cil para la gente, especialmente aquellos no muy apasionados sobre lo que hacen, el aceptar que hay mejores formas de hacer las cosas. No solo amenaza su comodidad, pero potencialmente sus carreras. Yo estaba en la escuela cuando Java iniciaba a ganar popularidad y qued� impresionado por lo cerrado de mente de los programadores que rehusaban aceptar que la recolecci�n de basura autom�tica, luego de corregir algunos menores problemas, podr�a ser algo muy �til (ni pensar en est�ndar). Ahora encuentro particularmente ir�nico ver programadores de Java reusando aceptar que los lenguajes din�micos podr�an convertirse en el nuevo Java (Especialmente dado que generalmente utilizan los mismos argumentos que los que usaban los programadores C++ contra Java)

Segundo, sin importar cuanto m�s eficiente es una tecnolog�a o t�cnica, siempre ser�s m�s eficiente en lo que sabes versus lo que est�s aprendiendo. Mi estrategia para sobrepasar esto es tomarme mi tiempo y reconocer que el proceso es una inversi�n de largo plazo. Adem�s si eres astuto, probablemente puedas introducir algo de investigaci�n en tu trabajo diario. Por astuto no quiero decir tramposo. Quiero decir que encuentres un proyecto secundario, no cr�tico. Aquel sistema de monitorizaci�n que quer�as hacer pero que nunca tuviste tiempo, o aquel prototipo que te solicitaron hacer. La aproximaci�n exacta que tomes va a depender de tu forma de aprender. Todo lo que puedo decir es que no debieras esperar un incremento de productividad de la noche a la ma�ana.

### En Este Cap�tulo ###
Eso fue mucho texto y poco c�digo. Este cap�tulo sent� las bases para los que contin�an, los que presentar�n mucho c�digo y ejemplos. Definimos lo que significa calidad para nosotros asi como las m�tricas que usaremos para medirlo (testabilidad). Miramos a la eficiencia y descubrimos que mientras parec�a f�cil de medir, no lo era. Toma un respiro y considera algo del c�digo que has escrito recientemente. Si hiciste tests, �Qu� podr�a haber hecho los tests m�s simples y que tuvieran menor posibilidad de fallar si el sistema cambia? Si no lo hiciste, �Puedes imaginar alg�n inconveniente o problema que enfrentar�as si decidieras hacer tests ahora?

## Cap�tulo 2 - Otra Introducci�n m�s a IoC ##
> "El prop�sito de la ingenier�a de software es controlar la complejidad, no crearla." - Pamela Zave

Dependiendo de que tecnolog�a uses, La Inversi�n de Control (IoC por sus siglas en ingl�s) y la Injecci�n de Dependencias (DI por sus siglas en ingl�s) puede o no que sean algo en lo que pases leyendo o inviertas energ�a. En algunos lenguajes, IoC y DI juegan un rol expl�cito en el desarrollo. En otros, es casi invisible. Eso no significa que IoC es menos importante o fundamental en algunos lenguajes que en otros. Lo que es diferente es el mecanismo usado para lograr IoC, que es lo realmente facinante del asunto y es el porqu� iremos a invertir un par de cap�tulos aprendiendo sobre esto.

Nuestro plan es iniciar con una corta introducci�n a IoC en este cap�tulo, luego examinaremos el problema de distintas perspectivas. El prop�sito no es etiquetar una aproximaci�n como mejor que otra, sino que expandir como vemos y nos enfrentamos a un desaf�o central que constantemente encontramos al programar. Cuando finalmente pude ver IoC m�s all� del estrecho entendimiento mediante el cual fui introducido, un nuevo mundo se abri� a mis ojos.  No porque este sea un conocimento que sacuda la tierra - de hecho quiz�s nisiquiera cambie tu forma de programar. Lo que hizo por mi fue validar la importancia de expandir mi conocimiento m�s alla de mi zona de comodidad. Me mostr� lo ignorante que era (y aun soy), y saber que eres ignorante es la clave para ser un programador exitoso.

### Unas palabras sobre Acoplamiento ##
Antes que iniciemos a examinar IoC, vamos a entender el problema que estamos tratando de solucionar. El acoplamiento es lo que obtienes cuando algo depende de otra cosa. Esa otra cosa puede ser una asignaci�n, un m�todo, una clase o incluso un sistema completo. Por ejemplo:

	#Incluso el c�digo m�s simple nos pueda acoplar a otra clase o implementaci�n:
	time = Time.now
	
	//...Algo un poco m�s complejo
	$('#logs').load('/orders/history', {id: _id});
	
	//...O algo mucho m�s grande
	var richList = Session.Query<Account>().Where(a => a.Amount > 10000000).List();


En cada uno de los ejemplos anteriores, nuestro c�digo es dependiente de alguna otra implementaci�n. Practicamente toda linea de c�digo que escribas, tecnicamente  hablando, va a generar acoplamiento. Gran parte del tiempo el acoplamiento es benigno (Nadie sugiere que realices envolturas para cada librer�a o dependencia), sin embargo casos m�s complejos terminan f�cilmente en problemas de testeabilidad, lo que indica que el c�digo es dif�cil de modificar y mantener. El �ltimo ejemplo es m�s obvio, dado que es imposible hacer tests sin efectibamente llegar a la base de datos (aunque hablaremos de esto en futuros cap�tulos ya que ir a la base de datos en un test no es para nada una mala idea).

El tipo de acoplamiento fuerte que queremos evitar es el que introduce dependencias entre componentes o sistemas. Incluso cuando sabes que la implementaci�n no va a cambiar, el acoplamiento har� dif�cil el refactoring y el mantenimiento.

### Bases de la Inversi�n de Control ###
Si el acoplamiento (que X sea dependiente de Y) es el problema, entonces la Inversi�n del control es la soluci�n. IoC es un termino que engloba carias soluciones que nos ayudan a desacoplar, o cuando menos, reducir el acoplamiento. La idea general es cambiar el flujo procedural por algo en lo cual se tenga mayor control. Para mejor entender el concepto, veamos la forma m�s comun de IoC en .Net: Injecci�n de Dependencias (DI).

El nombre *Injecci�n de Dependencias* dice mucho de lo que la t�cnica permite: Injectar dependencias en nuestro c�digo en vez de definirlas de manera est�tica (en duro). Estamos examinando primero esta forma de IoC no porque sea la m�s simple o sea la mejor, pero porque el resultado es particularmente explic�to y debido a que es una aproximaci�n independiente del lenguaje, del framewor o la tecnolog�a que estemos usando.

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

Este c�digo tiene dos dependencias de las que har�amos bien de desacoplarnos. La primera es `SqlDataStore` y la otra `BCrypt`. La idea detr�s de la Injecci�n de Dependencias es tomar estas dos dependencias y administrarlas hacia nuetstra clase o m�todo, en vez de tenerlas en duro. Esto puede ser logrado pasandolas como argumentos a nuestro m�todo, estableciendo propiedades en nuestra clase, o mediante el m�todo m�s com�n: entregarlas al constructor de la clase como argumentos. Cada aproximaci�n tiene sus propais ventajas y desventajas, pero todas proveen el mismo beneficio: externalizan la dependencia y en un mondo de tipos est�ticos, se puede programar contra interfaces. Aqu� vemos el ejemplo anterior re-escrito con Injecci�n de dependencia al nivel del constructor:

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

(Para dar un ejemplo completo hemos hecho que `UserRepository` implemente una interfaz tambi�n, de esa manera puede ser injectada hacia el c�digo que la utiliza).


Nuestro c�digo ahora nos escuda de la implementaci�n directa, haciendo m�s facil mantener, cambiar y probar la funcionalidad. Tambi�n, mientras algunos puedan encontrar que el m�todo `FindByCredentials` ahora es un poco m�s dificil de entender (con lo que estoy de acuerdo), si realmente te pones a pensar, vas a encontrar que la clase `UserRepository` como un todo es m�s entendible. Puedes f�cilmente mirar el costructor de `UserRepository` y entender *como* logra lo que hace. Otro beneficio, del cual hablaremos m�s adelante, es que la injecci�n por constructor ayuda a mantener nuestras clases cohesivas (a tener un prop�sito acotado y bien definido) - ya que al tener muchas dependencias generalmente significa que la clase est� haciendo demasiadas cosas.

Del ejemplo anterior debiera ser evidente c�mo se ver�an las injecciones mediante propiedad o m�todo. Injectar a un m�tod es �til solo cuando ese m�todo tiene una dependencia espec�fica (pero debiera ser usado de manera muy espor�dica ya que un uso muy frecuente indica falta de cohesi�n entre la clase y los m�todos). La injecci�n mediante propiedades es ideal para dependencias opcionales (Que tambi�n son bastante raras). La injecci�n mediante propiedad es tambi�n �til para el c�digo interno de los frameworks, donde deseas que las clases que hereden no necesiten tener constructores muy complejos.

### Frameworks de Injecci�n de Dependencias ###
En las comunidades donde DI es un patr�n com�n, los frameworks de DI son abundantes y muy populares, por lo que haremos de esta mensi�n  algo breve. Lo que necesitas saber es que el ejemplo que presentamos previamente, cuando es hecho de manera manual, puede a�adir una cantidad considerable de sobrecarga a nuestra programaci�n. Si nuestro c�digo desde la interfaz de usuario hasta los servicios externos (bases dedatos, servicios web, etc) tiene 4 o 5 niveles de profundidad y nuestras clases en promedio tienen 1 a 3 depndencias, entonces instanciar y rastrear nuestros objetos no va a ser muy divertido.

Es en enste pundo donde los frameworks de Injecci�n de dependencia entran al juego. Los configuras con las dependencias que neceistas usar y luego dejas que el framework los administre y se preocupe de crear los objetos. Puedes pensar en ellos como en una super f�brica de objetos, que puede darse cuenta cuales son los servicios que una clase necesita y se los administra de manera autom�tica, para entregarte una clase y todo su �rbol de dependencias creado y listo para usar. 

Veremos ahora un ejemplo de esto utilizando [Ninject](http://ninject.org/). La primera cosa que haremos es configurar nuestro framework DI. Los detalles de como se hace var�an de un framework a otro. Ninject utiliza una configuraci�n fluida.

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

El framework DI ver� que le solicitamos un �IUserRepository�, entonces revisa en su configuraci�n que necesita entregar un `UserRepository`. En ese momento, revisa el constructor y entiende que tiene dos dependencias. Nuevamente revisa su configuraci�n y encuentra estas dependencias, as� que las crea y las injecta, y de esta forma es capaz de entregarnos una instancia lista para usar.

Mant�n en mente que el objetivo de un framework DI no es hacer el c�digo dinamicamente enlazable. Queremos ser capaces de programar contra interfaces injectadas donde sea necesario. Es algo que podemos hacer de manera manual, pero incluso ejemplos simples son un verdadero dolor. Un framework DI automatiza una pequela pero importante parte del proceso (Creaci�n de objetos con dependencias).

Es dif�cil dejar pasar la oportunidad para quejarce por las configuraciones basadas en XML, asi que... La mayor�a de los frameworks de DI en .Net proveen tanto configuraciones por c�digo (como la que vimos arriba) como configuraciones mediante XML. El beneficio de usar configuraciones por c�digo es que tienes la capacidad de refactorizar y testear tus configuraciones. No hay ninguna ventaja con configuraciones en XML, aunque algunos programadores argumentar�n que con XML no necesitan recompilar para cambiar una dependencia. Yo digo que esos es basura: Un cambio en una configuraci�n de dependencia, independiente de donde se almacene, amerita el mismo proceso de QA y publicaci�n que cualquier otro cambio en la aplicaci�n.

### Anti patron de Injecci�n de Dependencias ###
Finalizar nuestra introducci�n a Injecci�n de dependencias con lo que hemos cubierto hasta ahora ser�a desfavorable. Hemos cubierto las mec�nicas de DI y los frameworks de DI, pero al enfocarnos en el *que* hemos introducido algunos feos *como*. Nuestra instancia de  `kernel` del ejemplo anterior es thread-safe, y podr�amos crear una clase est�tica y llamarla algo como `Factory.Get<T>` en todas partes de nuestro c�digo. Como sugerimos arriba, los frameworks de DI pueden verse como una suplantaci�n de el keyword `new`, as� que podr�a ser una buena aproximaci�n. 
	

Usar nuestro framework de DI de esta forma es conocido como el patr�n Service Locator, pero es generalmente percibido como un anti-patr�n. Uno necesita limitar el uso directo del framework DI. Si est�s usando un framework moderno, debieran haber puntos en los cuales puedas introducir la resoluci�n de dependencias mediante el framework DI. Por ejemplo. ASP.NET MVC 1 y 2 permiten que proveas un controller factory personalizado, que puede ser usado como punto de inicio para la resoluci�n de dependencias (La versi�n 3 tiene un modelo aun m�s simple) De hecho, la mayor�a de los frameworks DI proveer�n estas extensiones para diversos Frameworks, como es el caso del `NinjectHttpApplication` de ninject,  del cual simplemente heredas y le configuras los modelos y listo. Como un check simple, revisa cuantas veces est�s importanto el namespace de tu framework DI. No debieras encontrarlo en m�s de 4 o 5 lugares.
El punto es que con lenguajes de tipos est�ticos, los frameworks de DI debieran ser un ejercicio solo de configuraci�n que de programaci�n. Puede que te encuentres llamando al kernell de manera directa en las partes m�s bajas de tu c�digo, pero la resoluci�n de dependencias autom�tica debiera encargarse de ese punto en adelante. Si tu framework de DI no permite realizar esto, cambia el framework por uno m�s potente.

### En este Cap�tulo ###
En este cap�tulo hemos visto que es Inversi�n de Control y el problema que estamos tratando de solucionar con esto (reducci�n de acoplamiento). Tambi�n vimos un patr�n comun de IoC: la Injecci�n de dependencia. Para muchos programadores esta es una forma diferente de programar y pensar. En todo caso, recuerden que ganamos mucho de esto: El c�digo es m�s f�cil de cambiar y refactorizar, clases con baja cohesi�n son f�ciles de descubrir y los tests son m�s faciles de hacer.
