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

## Acerca del Traductor ##
David Lay es un desarrollador con experiencia principalmente en .Net con deseos de aprender y continuar aprendiendo otros paradigmas y plataformas. Ha dise�ado, implementado y mantenido varios sistemas de linea de negocio, tanto web como escritorio. Est� en una activa b�squeda por m�s entendimiento y siempre interesado en conocer personas que desafien sus puntos de vista y que le ense�en una o dos cosas (ojal� m�s).

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

Por un largo tiempo pensaba que la soluci�n era realmente as� de simple. Escribir tests y la calidad del c�digo ir�a incrementando. Pero m�s recientemente me he dado cuenta que no todos los tests son creados iguales y que es enteramente posible, si es que no com�n, tener realmente malos tests. Entender qu� es lo que hace a un tests bueno, y por lo tanto qu� es lo que hace al c�digo testeable, viene con la experiencia y espero, junto con los siguientes cap�tulos, pueda ayudarte a esquivar algunas de las piedras que me he encontrado en el camino. Es por esto que mucho de este libro estar� dedicado tanto a escribir tests como a la testeabilidad del c�digo. No mezcles testeabilidad como una m�trica con escribir tests. Es como escribir un mont�n de c�digo mantenible que no necesita mantenimiento. Es un objetivo, no una actividad. Ahora, es cierto que la mejor manera de descubrir que una soluci�n es testeable es mediante la escritura de un test. Eso s�, espero poder convencerte de que le des un intento; en los �ltimos tres a�os el convertirme en un escritor de tests efectivo es una de las cosas que m�s me ha ayudado a elevar mi habilidad. Sin embargo, es enteramente posible ver un m�todo o un sistema y estimar su testeabilidad, y por lo tanto, su calidad, sin escribir un test.

### Testeabilidad como una medida de calidad ###
No te culpo si eres esc�ptico. Todo lo que puedo hacer es prometer que mientras puede se que gastemos algo de tiempo escribiendo tests, no voy a tratar de hacerte sentir que est�s haciendo algo malo si elijes no hacer tests. Tambi�n, puedo mostrarte un ejemplo sencillo de lo que quiero decir:

	//Un ejemplo de c�digo dif�cil de probar, y por lo tanto, de mala calidad.
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
 
Este trozo de c�digo est� lejos de la perfecci�n. Si espec�ficamente lo miramos desde una perspectiva de la testeabilidad, podemos ver una cantidad de dependencias que lo har�n dif�cil de testear, como por ejemplo `SqlServerDataStore.FindUser` y `Response.Redirect`, por nombrar algunas. Lamentablemente muchas de estas vienen incluidas en el framework, lo que es uno de los motivos por los que muchos programadores .Net tienen tan fuertes sentimientos en contra de WebForms. En este caso en particular, la pr�ctica imposibilidad de hacer tests me dice que este c�digo va a ser dif�cil de cambiar y mantener.

Muchas de las mejores pr�cticas que escuchas por ah�, como YAGNI (you aren't going to need it; no lo vas a necesitar), bajo acople y alta cohesi�n, puede ser medido mediante la observaci�n del c�digo y pensando c�mo lo testear�as. Un m�todo que hace demasiado, potencialmente est� violando tanto YAGNI como la alta cohesi�n, y requerir� una cantidad dolorosa de c�digo inicial en un test, y probablemente va a ser muy f�cil de quebrar.

Hay un acr�nimo  en la programaci�n que se usa bastante: SOLID. Se refiere a cinco principios importantes del dise�o orientado a objetos: Single responsibility principle (Principio de responsabilidad �nica), Open/close principle (Principio abierto/cerrado), Liskov substitution principle (Principio de substituci�n de Liskov), Interface segregation principle (Principio de segregaci�n de interfaces) y Dependency inversion principle (Principio de inversi�n de dependencias). Estos son todos t�picos dignos de su propio cap�tulo, pero deber� bastar decir que muchos de ellos son algo ambiguos. �En qu� momento un nuevo comportamiento o mejora es considerado una responsabilidad o en cu�l se le asigna un componente? �Cu�ndo una interfaz se vuelve demasiado compleja? Estas son preguntas importantes y respuestas equivocadas van a tener consecuencias. La testeabilidad y la experiencia son herramientas que puedes usar para resolver esta ambig�edad. (Un buen lugar para comenzar a aprender sobre SOLID es en la <a href="http://en.wikipedia.org/wiki/Solid_(object-oriented_design)">Wikipedia</a>.)

### Eficiencia: No tan simple como parece ###
Puede que a�n no me creas sobre la testeabilidad como m�trica de calidad, pero conf�o en que crees que la calidad es un aspecto de suprema importancia. Otro de nuestros objetivos pragm�ticos es la eficiencia, debido a que no debemos demorarnos mucho en producir un c�digo de gran calidad. Uno esperar�a que la eficiencia en cuanto a aprender y mejorar, fuera algo f�cil de medir: puedo lograr XYZ ahora m�s r�pido de lo que lo hac�a antes, pero no es as�.

Primero que nada, y lo m�s peligroso, es que los programadores no siempre nos damos cuenta de que hay mejores formas de hacer las cosas. Seamos honestos, muchos de los programadores reh�sa aceptar solo la posibilidad que exista. Es dif�cil para la gente, especialmente aquellos no muy apasionados sobre lo que hacen, el aceptar que hay mejores formas de hacer las cosas. No solo amenaza su comodidad, pero potencialmente sus carreras. Yo estaba en la escuela cuando Java iniciaba a ganar popularidad y qued� impresionado por lo cerrado de mente de los programadores que rehusaban aceptar que la recolecci�n de basura autom�tica, luego de corregir algunos menores problemas, podr�a ser algo muy �til (ni pensar en est�ndar). Ahora encuentro particularmente ir�nico ver programadores de Java reusando aceptar que los lenguajes din�micos podr�an convertirse en el nuevo Java (Especialmente dado que generalmente utilizan los mismos argumentos que los que usaban los programadores C++ contra Java)

Segundo, sin importar cuanto m�s eficiente es una tecnolog�a o t�cnica, siempre ser�s m�s eficiente en lo que sabes versus lo que est�s aprendiendo. Mi estrategia para sobrepasar esto es tomarme mi tiempo y reconocer que el proceso es una inversi�n de largo plazo. Adem�s si eres astuto, probablemente puedas introducir algo de investigaci�n en tu trabajo diario. Por astuto no quiero decir tramposo. Quiero decir que encuentres un proyecto secundario, no cr�tico. Aquel sistema de monitorizaci�n que quer�as hacer pero que nunca tuviste tiempo, o aquel prototipo que te solicitaron hacer. La aproximaci�n exacta que tomes va a depender de tu forma de aprender. Todo lo que puedo decir es que no debieras esperar un incremento de productividad de la noche a la ma�ana.

### En Este Cap�tulo ###
Eso fue mucho texto y poco c�digo. Este cap�tulo sent� las bases para los que contin�an, los que presentar�n mucho c�digo y ejemplos. Definimos lo que significa calidad para nosotros as� como las m�tricas que usaremos para medirlo (testeabilidad). Miramos a la eficiencia y descubrimos que mientras parec�a f�cil de medir, no lo era. Toma un respiro y considera algo del c�digo que has escrito recientemente. Si hiciste tests, �Qu� podr�a haber hecho los tests m�s simples y que tuvieran menor posibilidad de fallar si el sistema cambia? Si no lo hiciste, �Puedes imaginar alg�n inconveniente o problema que enfrentar�as si decidieras hacer tests ahora?

## Cap�tulo 2 - Otra Introducci�n m�s a IoC ##
> "El prop�sito de la ingenier�a de software es controlar la complejidad, no crearla." - Pamela Zave

Dependiendo de que tecnolog�a uses, La Inversi�n de Control (IoC por sus siglas en ingl�s) y la Inyecci�n de Dependencias (DI por sus siglas en ingl�s) puede o no que sean algo en lo que pases leyendo o inviertas energ�a. En algunos lenguajes, IoC y DI juegan un rol expl�cito en el desarrollo. En otros, es casi invisible. Eso no significa que IoC es menos importante o fundamental en algunos lenguajes que en otros. Lo que es diferente es el mecanismo usado para lograr IoC, que es lo realmente fascinante del asunto y es el por qu� iremos a invertir un par de cap�tulos aprendiendo sobre esto.

Nuestro plan es iniciar con una corta introducci�n a IoC en este cap�tulo, luego examinaremos el problema de distintas perspectivas. El prop�sito no es etiquetar una aproximaci�n como mejor que otra, sino que expandir como vemos y nos enfrentamos a un desaf�o central que constantemente encontramos al programar. Cuando finalmente pude ver IoC m�s all� del estrecho entendimiento mediante el cual fui introducido, un nuevo mundo se abri� a mis ojos.  No porque este sea un conocimiento que sacuda la tierra - de hecho quiz�s ni siquiera cambie tu forma de programar. Lo que hizo por m� fue validar la importancia de expandir mi conocimiento m�s all� de mi zona de comodidad. Me mostr� lo ignorante que era (y aun soy), y saber que eres ignorante es la clave para ser un programador exitoso.

### Unas palabras sobre Acoplamiento ##
Antes que iniciemos a examinar IoC, vamos a entender el problema que estamos tratando de solucionar. El acoplamiento es lo que obtienes cuando algo depende de otra cosa. Esa otra cosa puede ser una asignaci�n, un m�todo, una clase o incluso un sistema completo. Por ejemplo:

	#Incluso el c�digo m�s simple nos pueda acoplar a otra clase o implementaci�n:
	time = Time.now
	
	//...Algo un poco m�s complejo
	$('#logs').load('/orders/history', {id: _id});
	
	//...O algo mucho m�s grande
	var richList = Session.Query<Account>().Where(a => a.Amount > 10000000).List();


En cada uno de los ejemplos anteriores, nuestro c�digo es dependiente de alguna otra implementaci�n. Pra�ticamente toda linea de c�digo que escribas, t�cnicamente  hablando, va a generar acoplamiento. Gran parte del tiempo el acoplamiento es benigno (Nadie sugiere que realices envolturas para cada librer�a o dependencia), sin embargo casos m�s complejos terminan f�cilmente en problemas de testeabilidad, lo que indica que el c�digo es dif�cil de modificar y mantener. El �ltimo ejemplo es m�s obvio, dado que es imposible hacer tests sin efectivamente llegar a la base de datos (aunque hablaremos de esto en futuros cap�tulos ya que ir a la base de datos en un test no es para nada una mala idea).

El tipo de acoplamiento fuerte que queremos evitar es el que introduce dependencias entre componentes o sistemas. Incluso cuando sabes que la implementaci�n no va a cambiar, el acoplamiento har� dif�cil el refactoring y el mantenimiento.

### Bases de la Inversi�n de Control ###
Si el acoplamiento (que X sea dependiente de Y) es el problema, entonces la Inversi�n del control es la soluci�n. IoC es un t�rmino que engloba carias soluciones que nos ayudan a desacoplar, o cuando menos, reducir el acoplamiento. La idea general es cambiar el flujo procedural por algo en lo cual se tenga mayor control. Para mejor entender el concepto, veamos la forma m�s com�n de IoC en .Net: Inyecci�n de Dependencias (DI).

El nombre *Inyecci�n de Dependencias* dice mucho de lo que la t�cnica permite: Inyectar dependencias en nuestro c�digo en vez de definirlas de manera est�tica (en duro). Estamos examinando primero esta forma de IoC no porque sea la m�s simple o sea la mejor, pero porque el resultado es particularmente expl�cito y debido a que es una aproximaci�n independiente del lenguaje, del framework o la tecnolog�a que estemos usando.

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

Este c�digo tiene dos dependencias de las que har�amos bien de desacoplarnos. La primera es `SqlDataStore` y la otra `BCrypt`. La idea detr�s de la Inyecci�n de Dependencias es tomar estas dos dependencias y administrarlas hacia nuestra clase o m�todo, en vez de tenerlas en duro. Esto puede ser logrado pas�ndolas como argumentos a nuestro m�todo, estableciendo propiedades en nuestra clase, o mediante el m�todo m�s com�n: entregarlas al constructor de la clase como argumentos. Cada aproximaci�n tiene sus propias ventajas y desventajas, pero todas proveen el mismo beneficio: externalizan la dependencia y en un mondo de tipos est�ticos, se puede programar contra interfaces. Aqu� vemos el ejemplo anterior re-escrito con Inyecci�n de dependencia al nivel del constructor:

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


Nuestro c�digo ahora nos escuda de la implementaci�n directa, haciendo m�s f�cil mantener, cambiar y probar la funcionalidad. Tambi�n, mientras algunos puedan encontrar que el m�todo `FindByCredentials` ahora es un poco m�s dif�cil de entender (con lo que estoy de acuerdo), si realmente te pones a pensar, vas a encontrar que la clase `UserRepository` como un todo es m�s entendible. Puedes f�cilmente mirar el constructor de `UserRepository` y entender *c�mo* logra lo que hace. Otro beneficio, del cual hablaremos m�s adelante, es que la Inyecci�n por constructor ayuda a mantener nuestras clases cohesivas (a tener un prop�sito acotado y bien definido) - ya que al tener muchas dependencias generalmente significa que la clase est� haciendo demasiadas cosas.

Del ejemplo anterior debiera ser evidente c�mo se ver�an las injecciones mediante propiedad o m�todo. Inyectar a un m�todo es �til solo cuando ese m�todo tiene una dependencia espec�fica (pero debiera ser usado de manera muy espor�dica ya que un uso muy frecuente indica falta de cohesi�n entre la clase y los m�todos). La Inyecci�n mediante propiedades es ideal para dependencias opcionales (Que tambi�n son bastante raras). La Inyecci�n mediante propiedad es tambi�n �til para el c�digo interno de los frameworks, donde deseas que las clases que hereden no necesiten tener constructores muy complejos.

### Frameworks de Inyecci�n de Dependencias ###
En las comunidades donde DI es un patr�n com�n, los frameworks de DI son abundantes y muy populares, por lo que haremos de esta menci�n algo breve. Lo que necesitas saber es que el ejemplo que presentamos previamente, cuando es hecho de manera manual, puede a�adir una cantidad considerable de sobrecarga a nuestra programaci�n. Si nuestro c�digo desde la interfaz de usuario hasta los servicios externos (bases de datos, servicios web, etc) tiene 4 o 5 niveles de profundidad y nuestras clases en promedio tienen 1 a 3 dependencias, entonces instanciar y rastrear nuestros objetos no va a ser muy divertido.

Es en este pundo donde los frameworks de Inyecci�n de dependencia entran al juego. Los configuras con las dependencias que necesitas usar y luego dejas que el framework los administre y se preocupe de crear los objetos. Puedes pensar en ellos como en una s�per f�brica de objetos, que puede darse cuenta cuales son los servicios que una clase necesita y se los administra de manera autom�tica, para entregarte una clase y todo su �rbol de dependencias creado y listo para usar. 

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

El framework DI ver� que le solicitamos un �IUserRepository�, entonces revisa en su configuraci�n que necesita entregar un `UserRepository`. En ese momento, revisa el constructor y entiende que tiene dos dependencias. Nuevamente revisa su configuraci�n y encuentra estas dependencias, as� que las crea y las inyecta, y de esta forma es capaz de entregarnos una instancia lista para usar.

Mant�n en mente que el objetivo de un framework DI no es hacer el c�digo din�micamente enlazable. Queremos ser capaces de programar contra interfaces injectadas donde sea necesario. Es algo que podemos hacer de manera manual, pero incluso ejemplos simples son un verdadero dolor. Un framework DI automatiza una peque�a pero importante parte del proceso (Creaci�n de objetos con dependencias).

Es dif�cil dejar pasar la oportunidad para quejarse por las configuraciones basadas en XML, as� que... La mayor�a de los frameworks de DI en .Net proveen tanto configuraciones por c�digo (como la que vimos arriba) como configuraciones mediante XML. El beneficio de usar configuraciones por c�digo es que tienes la capacidad de refactorizar y testear tus configuraciones. No hay ninguna ventaja con configuraciones en XML, aunque algunos programadores argumentar�n que con XML no necesitan recompilar para cambiar una dependencia. Yo digo que esos es basura: Un cambio en una configuraci�n de dependencia, independiente de donde se almacene, amerita el mismo proceso de QA y publicaci�n que cualquier otro cambio en la aplicaci�n.

### Anti patron de Inyecci�n de Dependencias ###
Finalizar nuestra introducci�n a Inyecci�n de dependencias con lo que hemos cubierto hasta ahora ser�a desfavorable. Hemos cubierto las mec�nicas de DI y los frameworks de DI, pero al enfocarnos en el *que* hemos introducido algunos feos *como*. Nuestra instancia de  `kernel` del ejemplo anterior es thread-safe, y podr�amos crear una clase est�tica y llamarla algo como `Factory.Get<T>` en todas partes de nuestro c�digo. Como sugerimos arriba, los frameworks de DI pueden verse como una suplantaci�n de el keyword `new`, as� que podr�a ser una buena aproximaci�n. 
	

Usar nuestro framework de DI de esta forma es conocido como el patr�n Service Locator, pero es generalmente percibido como un anti-patr�n. Uno necesita limitar el uso directo del framework DI. Si est�s usando un framework moderno, debieran haber puntos en los cuales puedas introducir la resoluci�n de dependencias mediante el framework DI. Por ejemplo. ASP.NET MVC 1 y 2 permiten que proveas un controller factory personalizado, que puede ser usado como punto de inicio para la resoluci�n de dependencias (La versi�n 3 tiene un modelo aun m�s simple) De hecho, la mayor�a de los frameworks DI proveer�n estas extensiones para diversos Frameworks, como es el caso del `NinjectHttpApplication` de ninject,  del cual simplemente heredas y le configuras los modelos y listo. Como un check simple, revisa cuantas veces est�s importando el namespace de tu framework DI. No debieras encontrarlo en m�s de 4 o 5 lugares.
El punto es que con lenguajes de tipos est�ticos, los frameworks de DI debieran ser un ejercicio solo de configuraci�n que de programaci�n. Puede que te encuentres llamando al kernell de manera directa en las partes m�s bajas de tu c�digo, pero la resoluci�n de dependencias autom�tica debiera encargarse de ese punto en adelante. Si tu framework de DI no permite realizar esto, cambia el framework por uno m�s potente.

### En este Cap�tulo ###
En este cap�tulo hemos visto que es Inversi�n de Control como tambi�n el problema que estamos tratando de solucionar (reducci�n de acoplamiento). Tambi�n vimos un patr�n com�n de IoC: la Inyecci�n de dependencia. Para muchos programadores esta es una forma diferente de programar y pensar. En todo caso, recuerden que ganamos mucho de esto: El c�digo es m�s f�cil de cambiar y refactorizar, clases con baja cohesi�n son f�ciles de descubrir y los tests son m�s f�ciles de hacer.

## Cap�tulo 3 - IOC de cabeza ##
> "Si no elevas la mirada, vas a pensar que eres el punto m�s alto" - Antonio Porchia

Al comenzar el aprendizaje de IoC y realizar los primeros experimentos con un framework de DI, nunca te preguntas si hay otra forma de resolver dependencias. DI es bastante simple y a la vez hace juego con la forma en que la mayor�a de la gente organiza su c�digo .Net o Java. DI es un patr�n adecuado para programaci�n orientada a objetos en lenguajes est�ticos... pero cambia a un paradigma diferente y encontrar�s soluciones diferentes.

### Cambio de mente din�mico ###
Es com�n para los desarrolladores pensar que los lenguajes din�micos y el tipado din�mico son sin�nimos. Es cierto que muchos (pero no todos) los lenguajes din�micos tienen un sistema de tipos din�mico. Pero el hecho es que los lenguajes din�micos realizan muchas cosas en tiempo de ejecuci�n que en un lenguaje est�tico se hacen al momento de compilar. La implicancia es que con un lenguaje din�mico los desarrolladores tienen mayores capacidades en tiempo de ejecuci�n que sus contrapartes est�ticas.

Al principio este poder extra puede verse como de poca utilidad. Despu�s de todo, �Qu� tan frecuentemente necesitas cambiar el c�digo en tiempo de ejecuci�n? Bueno, como es en la mayor�a de los casos, no sabemos lo que necesitamos hasta que lo tenemos a disposici�n y luego nos preguntamos qu� hac�amos antes de tenerlo. Pi�nsalo en t�rminos de las caracter�sticas a�adidas a C# con el paso del tiempo: tipos gen�ricos (Generics), m�todos an�nimos, LINQ (por nombrar algunos). Un runtime din�mico es lo mismo, el impacto es dif�cil de comprender mientras est�s restringido por tus experiencias en lenguajes est�ticos. Reflection no es una parte integral de tu c�digo porque es limitado y complicado; pero si fuera poderoso y simple probablemente ser�a una herramienta que utilizar�as d�a a d�a (para ser honesto, comparar los lenguajes din�micos con Reflection es tremendamente injusto para los lenguajes din�micos, pero solamente estamos tratando de establecer algunos paralelos)

�Qu� tiene esto que ver con la Inversi�n de Control? La naturaleza flexible de los lenguajes din�micos significan que IoC est� directamente implementado en la mayor�a de los lenguajes din�micos. No hay necesidades de inyectar par�metros o usar frameworks. Simplemente utiliza las capacidades del lenguaje. Veamos un ejemplo:

	class User
	  def self.find_user(username, password)
	    user = first(:conditions => {:username => username})
	    user.nil? || !Encryptor.password_match(user, password) ? nil : user
	  end
	end
    
Nuestro c�digo tiene dos dependencias: `first` va a acceder a un almacenaje subyacente (lo que puede que no sea obvio si no eres familiar con Ruby) y `Encryptor` es una clase inventada para comparar el hash del password del usuario junto con el entregado. En un mundo est�tico ambos ser�an complicados. En Ruby y otros lenguajes din�micos es simplemente asunto de cambiar la implementaci�n de `first` y `Encryptor`:

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
    
Mant�n una mente abierta y recuerda que este c�digo puede ser tan misterioso para ti como m�todos an�nimos y lambdas para otras personas. Discutiremos el c�digo en m�s detalle pero primero miraremos a c�mo es utilizado:

	it "returns the found user" do
	  user = User.new
	  first_returns(user)
	  password_match_returns(true)
	  User.find_user('leto', 'ghanima').should == user
	end
    
En la vida real utilizar�as un framework de mocking para que se haga cargo de esto y que provea una sintaxis m�s limpia y otras caracter�sticas m�s poderosas. Pero, haciendo a un lado un poco de magia, podemos ver que nuestros dos m�todos redefinen los m�todos `first` y `password_match` en tiempo de ejecuci�n para que implementen un comportamiento que nuestros test pueden utilizar. Para realmente iniciar a entender esto necesitaremos cubrir clases "Singleton" (de solo una instancia).

#### Singleton y Metaclases ####

En C#, Java y muchos de los dem�s lenguajes est�ticos, una clase puede seguramente verse como una plantilla r�gida. Uno define campos y m�todos y compila el c�digo usando las clases como un contrato inmutable. Las clases sirven un prop�sito muy �til como una herramienta de dise�o. El problema de las clases, sin ser culpa de ellas, es que muchos desarrolladores piensan que las clases y la programaci�n orientada a objetos son una y la misma. No lo son. La programaci�n orientada a objetos, como el nombre indica, es acerca de los objetos. En lenguajes est�ticos esto significa instancias. Dado que las instancias est�n fuertemente ligadas con su respectiva clase, es f�cil entender por qu� los desarrolladores mezclan los conceptos.

Pero si miras m�s all� de los lenguajes est�ticos y veras una historia distinta. No solo no hay ley que diga que las clases no puedan ser entes vivos por s� mismos, sino que tambi�n ver�s que la programaci�n orientada a objetos puede existir felizmente sin clases. El mejor ejemplo con el que probablemente ya eres familiar es JavaScript. Contempla la POO sin clases:
 
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
   
Como siempre, el punto no es que una forma es mejor que la otra, sino obtener distintas perspectivas. Si haces POO de una sola forma por mucho tiempo, terminar�s comprometiendo tu capacidad para crecer como profesional.

Si bien la orientaci�n a objetos no *requiere* de clases, son muy �tiles como plantillas. Es en este punto donde Ruby y las clases singleton brillan; porque como lo hemos mencionado, no hay ley que diga que una clase no pueda cambiar.

En Ruby todo objeto tiene su propia clase, llamada una clase singleton. Esto te permite definir miembros en instancias espec�ficas, por ejemplo:

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

T�cnicamente no estamos a�adiendo el m�todo `is_over_9000?` al objeto `goku`, sino que lo estamos agregando a la clase singleton oculta de la cual el objeto `goku` hereda y por lo tanto tiene acceso. Decimos que la clase singleton es invisible porque tanto `goku.class` y `vegeta.class` retornan `Sayan`. Hay formas de exponer la clase singeton, pero cuando no est�s haciendo metaprogramaci�n, las clases singleton son transparentes.

Para obtener acceso a la clase singleton, que es en si un objeto real, usamos la sintaxis `class << ` syntax. Por ejemplo, el m�todo `is_over_9000?` podr�a ser definido de la siguiente manera:

	class << goku
		def is_over_9000?
			true
		end
	end
    
Si queremos asignar la clase singleton a una variable, podemos simplemente exponer `self`:

	singleton = class << goku
		self
	end
	
	#o m�s comun y conciso, usando ; en vez de saltos de l�nea
	singleton = class << goku; self; end

Interesantemente (y no estoy seguro de porqu� lo encuentro interesante), si observamos a las instancias `goku` and `singleton` obtenemos el siguiente resultado:

	goku
	=> #<Sayan:0x10053a1f0>
	singleton
	=> #<Class:#<Sayan:0x10053a1f0>>

En Ruby, todo es un objeto, incluso una clase es un objeto (que hereda de `Class`, que a su vez hereda de `Object`). Esto significa que puedes invocar m�todos en tus clases:

	Sayan.is_a?(Object)
	=> true
	Sayan.is_a?(Integer)
	=> false
	Sayan.to_s
	=> "Sayan"
    
 Dado que las clases son objetos, tambi�n tienen clases singleton (que generalmente son llamadas metaclases). Podemos tener acceso a la metaclase de una clase mediante la misma sintaxis anterior `class <<`:
 
	metaclass = class << Sayan
		self
	end
	#or, the more consice approach
	metaclass = class << Sayan; self; end

Las clases Singleton no son realmente algo con lo que estar�s trabajando muy seguido, pero son importantes porque los m�todos de las clases son definidos en sus metaclases. Los m�todos de una clase son muy similares a los m�todos est�ticos en lenguajes como C# o Java. Son definidos en dos posibles formas y son usados de la forma que esperar�as:

	class Sayan
		# Primera forma de definir un m�todo de clase, usando self.nombreDeMetodo
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

La diferencia clave entre los m�todos de clase en Ruby y los m�todos est�ticos en Java/C# es que las los m�todos de clase son definidos en la metaclase que es un objeto. Dicho de otra forma, mientras los m�todos de clase puedan parecerse a m�todos est�ticos, son en realidad m�s similares a m�todos de instancia.

�Qu� sacamos de todo esto? Mucha de la rigidez que encontrar�s en un lenguaje est�tico no existe en un lenguaje din�mico. Clases selladas, metodos no virtuales y m�todos est�ticos, que son mecanismos para prevenir que hagas ciertas cosas, desaparecen. Hay pros y contras a cada paradigma, pero no hay raz�n para dejar de conocer a cada uno.

Quiero, eso si, dejar claro que desde el punto de vista de la capacidad de prueba, tiene muchas ventajas. - la dificultad de probar un m�todo est�tico `password_match` en C# debiera ser prueba suficiente de que no podemos simplemente sobrescribir la implementaci�n como hicimos en el inicio del cap�tulo, simplemente porque las clases no son objetos. DI, o siquiera las interfaces no son necesarias en Ruby. El desacople que se logra en C# mediante inyecci�n de interfaces y administraci�n de dependencias es reemplazado por la propia naturaleza del lenguaje Ruby.

### Eventos / Callbacks ###
Otra forma de reducir el acoplamiento es utilizando eventos y callbacks. Es bien conocido que los eventos, por su propia naturaleza, proveen protecci�n contra el acoplamiento. El c�digo que lanza un evento declara *no me interesa quien eres o lo que vas a hacer, pero es tiempo de hacerlo.* Puede haber 0 manejadores, o cientos y pueden hacer un conjunto de cosas sin relaci�n entre ellas, pero nada de eso le importa a quien lanza el evento. El c�digo termina siendo f�cil de probar ya que desde el punto de vista del emisor, solo tienes que probar que el evento ha sido emitido y desde el punto de los interesados, que el m�todo ha sido subscrito.

La raz�n por la cual no usamos eventos en todas partes es porque simplemente no se ajustan al flujo lineal que usamos para la mayor�a de nuestro c�digo. Sin embargo, en los �ltimos a�os esto ha empezado a cambiar. �Por qu�? El renacer de JavaScript. Ahora tenemos mucho m�s c�digo en JavaScript y muchos programadores est�n abandonando sus percepciones (generalmente negativas) y aprendiendo el lenguaje. JavaScript ya no es un lugar en donde baste confiar en hacks y esperar que todo siga funcionando. Ha habido un cambio hacia un JavaScript de calidad y mantenible. Esto significa que necesitamos comenzar a preocuparnos del acoplamiento, la cohesi�n y la testeabilidad. Cuando se trata de aquello, eventos son en JavaScript lo que DI es para Java/C# o metaprogramaci�n es para Ruby.

Digamos que eres un maestro de [jQuery](http://www.jquery.com/) (si no lo eres, puedes saltar al Apendice A y B para iniciar esa jornada cuando quieras) y has construido una cantidad de plugins. Estas son cosas que planeamos reusar a lo largo de nuestro sitio. Muchas de estas plugins van a necesitar  interactuar con las dem�s. Por ejemplo, una de las plugins convierte una simple lista de filas en una rejilla ordenable y paginable y otra permite que un formulario sea enviado mediante AJAX. Por supuesto, cuando el usuario env�a un nuevo registro mediante el formulario AJAX, la rejilla debe actualizarse. Primero veamos la configuraci�n b�sica:

	// aplica el plugin fancyGrid al elemento con el id users
	$('#users').fancyGrid();
	
	// aplica el plugin fancySubmit al elemento con el id add_user
	$('#add_user').fancySubmit();

El centro de nuestra plugin `fancySubmit` ser�a algo tan simple como:

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

(Si jQuery no te es familiar, este c�digo est� interceptando el evento `submit` del formulario para enviar los datos mediante AJAX. La respuesta es luego manejada por la funci�n `handleResponse`. Nuevamente, quiz�s quieras saltar a los Ap�ndices A y B para tomar velocidad en jQuery.)

`handleResponse` puede manejar casos gen�ricos (errores, validaci�n) directamente, pero cualquier cosa m�s espec�fica va a depender del contexto en el cual est� siendo usado. �La soluci�n? Permitir que un callback sea entregado al plugin y llamarlo cuando sea tiempo.

	handleResponse: function(r){
		// agregar aqu� (quiz�s) alg�n manejo generico
		if (options.onSubmit != null) { options.onSubmit(r); }
	}

Con este cambio tan simple ahora podemos enlazar las dos plugins sin que una sepa de la otra:

	// Aplica el plugin fancyGrid al elemento con el plugin users
	var $users = $('#users').fancyGrid();
	
	// Aplica el plugin fancySubmit al elemento con el id add_user
	$('#add_user').fancySubmit({
		onSubmit: function(r) { $users.fancyGrid('newRow', r); }
	});

Usando esta forma, las dos plugins trabajan juntas sin saber nada una de la otra. esto ayuda a asegurar que tu c�digo se mantenga altamente reusable y cohesivo.

### Poniendolo a prueba ###
Podemos probar `handle response` entregando un callback falso que pueda hacer algunas verificaciones b�sicas. Sin embargo, debemos asegurarnos en llamar a `$.post`. Debido a que JavaScript es din�mico como Ruby, tambi�n provee mecanismos para cambiar nuestras definiciones en tiempo de ejecuci�n. Combinando nuestra reimplementacion dinamica con nuestros callbacks personalizados obtenemos:

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

Ignora la llamada a `expect` por ahora, llegaremos a eso en un minuto. Reimplementamos la funci�n `$.post`, evadiendo la pesada implementaci�n real con algo m�s manejable. `$.post` esencialmente solo ejecuta el tercer par�metro (que si recordamos, arriba en el plugin, es una llamada a `self.handleResponse`) con parametros preestablecidos. Luego, inicializamos el plugin con nuestro callback, el cual va a asegurar que el par�metro entregado sea el que esperamos. Finalmente enviamos el formulario para ejecutar el c�digo real.

Acerca el llamado a `expect`, esto le dice a nuestro framework, [Qunit](http://docs.jquery.com/Qunit) en este caso, que debe esperar una llamada al m�todo. Esto es lo principal cuando se trabaja con callback y eventos. �Qu� podria pasar si no llamamos `expect` y adem�s modificamos nuestro plugin para no llamar al callback? Todavi� pasar�amos esta prueba porque nunca nada ser�a asegurado. Especificando `expect(1)` nos aseguramos que nuestra expectativa real (que nuestro callback sea llamado una vez, no m�s ni menos, y con los par�metros correctos) es invocada. Si `ok` no es llamado, entonces `expect` va a fallar y sabremos que algo anda mal.

La introducci�n de m�todos an�nimos y lamdas hacen posible que se escriba c�digo similar en c#, que aveces es incluso mejor que lo que normalmente se escribe.

### En este Cap�tulo ###

Dependiendo de tu experiencia con Ruby y jQuery, este cap�tulo puede haber sido sobrecogedor. Cubrimos algunos conceptos avanzados en lenguajes que son menos familiares para nosotros. Posiblemente elegimos la parte m�s complicada de Ruby para meter nuestras narices (metaprogramaci�n), as� que no te desanimes si algo (o mucho) se te ha escapado. Tambi�n vimos algunos escenarios de pruebas bien distintos. M�s importante, en todo caso, fue como pudimos volver a aprender algo que ya conoc�amos bien (IoC) explorando cosas que para otras personas, son fundamentales. Con confianza puedes considerar IoC como una caracter�stica incluida en Ruby, de manera muy similar a como se puede ver que LINQ es una caracter�stica incluida en C#. Incluso si no entiendes las complicaciones de el codigo o las implicaciones que tiene en la programaci�n cotidiana, este cap�tulo puede a�n mostrar el valor de aprender y crecer.