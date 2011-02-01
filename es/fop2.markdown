# Fundaciones de Programaci�n 2 #
> "Si al principio no resulta, intenta, intenta, intenta otra vez" - William E. Hickson

## Licencia ##
Fundaciones de Programaci�n 2 est� bajo la licencia Attribution-NonCommercial 3.0 Unported. **Este libro no le debiera haber costado dinero**

Eres libre de copiar, distribuir, modificar y/o compartir el libro. Sin embargo, solicito que siempre atribuyas este libro a mi, Karl Seguin, y que no lo uses para prop�sitos comerciales.

Puedes ver el texto completo de la licentia en:
<http://creativecommons.org/licenses/by-nc/3.0/es/legalcode.es>

## �ltima Revisi�n ##
Este libro est� actualmente en desarrollo, el lanzamiento final est� esperado para inicios de Febrero de 2011

Para obtener la �ltima versi�n, visita <http://github.com/karlseguin/foundations2>.

## Acerca del Autor ##
Karl Seguin es un desarrollador con experiencias en varios campos y tecnolog�as. Es un experto desarrollador en .Net y aprendiendo Ruby. Es familiar con todos los aspectos de el desarrollo web, concurrencia y programaci�n de Sockets y varias tecnolog�as SQL y NOSQL. Es un contribullente semi-activo de proyectos de c�digo abierto, escritor t�cnico y un exponente espor�dico.

Su blog puede ser accedido desde <http://openmymind.net>, y sus tweets via [@karlseguin](http://twitter.com/karlseguin)

El es tambi�n el fundador de servicios gratuitos para desarrolladoradores de juegos en <http://mogade.com>.

## Introduction ##
I'm always amazed by the number of passionate programmers I run into. So much of our life is dedicated to work that we are fortunate for the opportunity to spend that time doing what we love. This isn't a unique property of programmers, but it's uncommon enough to be surprising to most people. "You go home and *work* every day?" we are asked. Only our closest friends, and passionate colleagues really understand that *work* has two meanings for us, neither of which is a 9-5 drudge.

You've probably noticed that enthusiasm and drive is a pretty critical thing to have in such a young field. Technology continues to change at a rapid pace, the field is growing, and systems are getting increasingly complex. The result is a clear divide between programmers who love their craft and those who don't. You're either learning, trying and sometimes failing, or you're stuck in the past, likely oblivious to just how far behind you've fallen.

Unfortunately, being passionate about what you do isn't always enough. We all have different strengths and weaknesses, different ways to learn, and different tolerance towards failure. There's also a constant stream of new technologies which makes it hard to figure out what to spend your time learning. The truth is that I'm not a great programmer. I'm a good programmer who likes to learn (and teach) and who enjoys playing with technology. I've seen people pick up new languages in days when it's taken me months, or write algorithms that I had to pretend to agree with because I just wasn't following. The Foundations of Programming series is meant to help people like me, people who care about what they do, want to do it better, but aren't always sure how to proceed.

I hope this book will help you.

### With Respect To The Original ###
The [original Foundations of Programming](https://github.com/karlseguin/Foundations-of-Programming-Ebook) has been, by my own standards, a success. It seems to have genuinely helped developers and served a need which clearly needed serving. Each book, the original and this one, stand on their own; they are independent from each other. However, I would suggest that if you plan on reading the original, you do so before continuing with this book. My views have matured and in some cases changed or clarified. I think much can be gained by seeing how I've evolved as a programmer.

## Chapter 1 - Quality and Efficiency ##
>"Quality is never an accident; it is always the result of intelligent effort." - John Ruskin

Pragmatically, the reason I, and I assume most programmers, are keen to learn is to improve the quality of the code we write as well as our efficiency. I don't know any programmer who spends time learning new approaches and technologies with the explicit goal of being able to write worse code, or find ways to slow his or her pace. How do we measure efficiency and quality though? What, as creators, do we consider to be our goals?

Management-type might solely align quality with client/user satisfaction. While that's certainly important, good programmers are almost always the stakeholders with the highest quality expectation as well as being the most critical. As DeMarco and Lister said in Peopleware, **We all tend to tie our self-esteem strongly to the quality of the product we produce - not the quantity of the product, but the quality;.** I find it difficult to put quality, from a programmer's perspective, into words; yet, I'm sure most of us not only have a similar definition, we can all easily recognize it (or the lack of it). Quality is about coming up with an elegant solution to a problem - both at the micro (an individual behavior) and macro levels (the system as a whole). What's *elegant* then? It varies on the context of the problem, but generally, an elegant solution is both the simplest possible one as well as the most explicit and easy to understand.

The more I've programmed, the more I've noticed something truly startling. Not only is the simplest solution obviously the easiest to implement, it's almost certainly the easiest to understand, maintain and change. Simple solutions also tend to have as good or better performance characteristics than more complex approaches. This is particularly astounding when you find yourself knee-deep in an over-engineered mess where the original intention for flexibility, performance and efficiency are sabotaged by artificial complexity. That doesn't mean I advocate programming without consideration of design. Instead, I believe that given some experience and reflection, a balance between forward-thinking design and pragmatism isn't only achievable, it's quite natural?

I wish I could tell you the answer. It isn't that I don't know. The problem is that I have to preface it with a word of warning; else I risk having you roll your eyes and give up on this book. I know a lot of you are sick of hearing about it, but I beg that you hear me out and recognize that I'm probably not saying what you think I'm saying. Deal? So the secret to writing quality code is to make sure your code is testable. WAIT...don't roll those eyes, I'm not saying that you have to test your code (and I'm certainly not saying that you shouldn't). I'm just saying that if, theoretically, you were to test your code, it shouldn't be hard to do. Code can be testable without actually testing it - and ultimately, at the most fundamental level, that's what you should be aiming for.

For a long time I thought the solution really was that simple - write tests, and the quality of your code will greatly improve. More recently though I've realized that not all tests are created equally and it's entirely possible, if not common, to have really poor tests. Understanding what makes a good test, and thus what makes code testable, comes with experience, and hopefully, through future chapters, I can help you avoid some of the pitfalls I ran into. Therefore, much of this book is going to be devoted to both writing tests and testability. Do not mix testability as a quality metrics with writing tests. It's a lot like writing maintainable code that doesn't really require maintenance - it's a goal, not an actual activity.  Now it's true that the best way to discover whether a solution is testable is to actually write tests. I do hope that I can convince you to give it a try; in the last three years, becoming an effective test writer has been one of the two things which has most helped me elevate my craft. Nonetheless, it's entirely possible to look at a method, or a system, and gauge testability, and thus quality, without actually writing a test.

### Testability as a Quality Metric ###
I don't blame you if you're skeptical. All I can do is promise that, while we might spend some time on writing effective tests, I won't try to make you feel like you are doing something wrong if you choose not to test. Also, I can show you a simple example of what I mean:

	//An example of hard to test, and thus low-quality, code
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
(If this was a short-lived/throw away app, we might forgive it. Although I must say that in my experience, skilled programmers write clean and thoughtful code regardless of the expected life expectancy of our code. This is likely due to the fact that we all know *prototype* code can end up having an embarrassingly long shelf-life.)
 
This snippet is far from perfect. If we specifically look at it from a testing point of view, we'll see a number of dependencies which will make this hard to test, such as `SqlServerDataStore.FindUser` and `Response.Redirect`, to name a few. Sadly, many of those are baked into the framework - which is a one of the reasons many .NET developers feel so strongly against WebForms. In this particular case, the near impossibility of testing tells me that the code will be difficult to change and maintain.

A lot of the best practices you hear thrown around, like YAGNI (you aren't going to need it), low coupling and high cohesion can be measured by looking at your code and thinking of how you'd test it. A method that does too much, potentially violating both YAGNI and high cohesion, will require a painful amount of setup code to test (as well as prove easy to break).

There's a programming acronym that gets used a lot called SOLID. It stands for five important principles of object-oriented design: Single responsibility principle, Open/close principle, Liskov substitution principle, Interface segregation principle and Dependency inversion principle. These are all topics worthy of their own chapter (there's an ideal), but suffice it to say that most of them are somewhat ambiguous. At what point is a new behavior or enhancement considered an additional responsibility of a given component? When has an interface become too complex? These are important questions and the wrong answer can will have consequences. Testability and experience are the tools you use to remove this ambiguity. (A good place to start to learn more about SOLID is <a href="http://en.wikipedia.org/wiki/Solid_(object-oriented_design)">Wikipedia</a>.)

### Efficiency: Not As Simple As It Seems ###
I might not have sold you on the testability as a quality metric (yet), but I'm confident you agree that quality is a supremely important aspect. Our other pragmatic-driven goal is efficiency, because great code can't wait forever. You'd hope that efficiency, with respect to learning and improving, would be easy to measure: can I achieve XYZ now faster than I could before? This isn't the case. 

First, and most dangerously, programmers don't always realize that a better way may exist. Let's be honest, a lot of programmers refuse to accept that very possibility. It's hard for people, especially those not passionate about what they do, to accept that a better way exists - it not only threatens their comfort zone, but potentially their careers. I was in school when Java started gaining popularity and was impressed by the close-mindedness of programmers who refused to accept that automatic garbage collection might, after working out some quirks, be a useful (let alone standard) general purpose solution. I find it particularly ironic now when Java developers refuse to accept that dynamic languages might become the new Java (especially since they often raise the same concerns which C++ developers once had about Java).

Secondly, regardless of how much more efficient a new technology or approach is, you'll be more efficient in what you know versus what you're learning. My strategy to surmount this is to take my time and recognize the process as a long term investment. Also if you are clever about it, you can probably fit some R&D into your day to day work. By clever, I don't mean deceitful. I mean finding secondary, non-critical systems. That monitoring system you've talked about with colleagues but never had time to do, or that prototype you've been asked to write. The exact approach you take will be personalized to your preferred way to learn. All I can say is that you shouldn't expect an increase in efficiency overnight.

### In This Chapter ###
That was a lot of text with too little code. This chapter was the groundwork for following chapters, which rely heavily on code and examples. We defined what quality means to us as well as the metric we'll use to measure it (testability). We looked at efficiency and discovered that while it might seem easy to gauge, it really isn't. Take a break and consider some of the code you've recently written. If you did test it, what could have made your tests simpler and less likely to fail as your system changes? If you didn't, can you think of any pain points you might have run into if you decided to test it now?

## Chapter 2 - Yet Another IoC Introduction ##
> "The purpose of software engineering is to control complexity, not to create it." - Pamela Zave

Depending on what technology you use, Inversion of Control (IoC) and Dependency Injection (DI) may or may not be something you read about and spend energy on. In some languages IoC and DI play a significant and explicit role in development. In others, it's barely visible. That doesn't mean that IoC is less important or fundamental in some languages than in others. What is different is the mechanism used to achieve IoC, which is what's truly fascinating about the subject and why we are going to spend the next couple chapters learning more about it.

Our plan is to start with a brief introduction on IoC in this chapter. Then we'll look at the problem from different perspectives. The purpose isn't to label one approach better than another. Rather, our goal is to expand how we see, and possibly approach, a core challenge we constantly face while coding. When I finally saw IoC beyond the narrow understanding that I was introduced to, I felt like a new world had been opened up to me. Not because this is earth shattering knowledge - in fact, it probably won't even change how you code. What it did for me was validate the importance of expanding my knowledge beyond my comfort zone. It reinforced how ignorant I was (and still am), and knowing that you are ignorant is key to being a successful programmer.

### A Word on Coupling ###
Before we look at IoC, let's understand the problem we are trying to solve. Coupling is what you get when something is dependent on something else. That something can be an assignment, a method, a class or even a whole system. Some examples:

	#The simplest code can couple us to another class or implementation
	time = Time.now
	
	//...Something slightly more complex
	$('#logs').load('/orders/history', {id: _id});
	
	//...Or something a lot bigger
	var richList = Session.Query<Account>().Where(a => a.Amount > 10000000).List();

In each of the above examples, our code is dependent on some other implementation. Practically every line of code you write will, technically speaking, generate coupling. A lot of the time coupling is benign - no one's suggesting that you wrap every core library/type. However, more complex cases often lead to testability challenges, which indicate that code is hard to change and maintain.  The last example is the most obvious as it's impossible to test without actually hitting the database (we'll talk more about that in a future chapter, because hitting the database isn't at all a bad idea).

The kinds of tight coupling we want to avoid are those that introduce dependencies between independent components or systems. Admittedly, saying that coupling makes it difficult to change the implementation isn't always compelling - sometimes you can be reasonably certain that the implementation is **not** going to change. However, tight coupling will also make it more difficult to maintain, reuse and refactor your code.

### Inversion of Control Basics ###
If coupling (having X depend on Y) is the problem, then Inversion of Control is the solution. IoC is an umbrella term for various solutions that help us decouple or, at the very least, loosen coupling. The general idea is to change the normal (procedural) flow for something you have greater control over. To better understand the concept, let's look at the most common form of IoC in the .NET/Java world: Dependency Injection (DI).

The name *Dependency Injection* is pretty telling of what the practice entails: injecting dependencies into our code rather than statically defining them (hard coding). We look at this form of IoC first not because it's better or simpler, but because the result is particularly explicit and because it's an approach that is independent of the language/framework/technology we are using.

Take the following example:

	public class UserRepository
	{
		public User FindByCredentials(string username, string password)
		{
			var user = SqlDataStore.FindOneByNamedQuery("FindUserByUserName", new {username = username});
			if (user == null) { return null; }
			return BCrypt.CheckPassword(user.Password, password) ? user : null;
		}
	}

This code has two dependencies which we'd do well to decouple: the first being `SqlDataStore` and the other the `BCrypt` library. The idea behind Dependency Injection is to take those two dependencies and supply them to our class/method, rather than having them hard coded. This can be done by passing them as arguments to our method, setting properties of our class, or, the most common approach, supplying them as constructor arguments. Each approach has its own advantages and drawbacks. They all provide the same benefits though: we externalize our dependencies and, in a statically typed world, can program against an interface. Here's the same code using Dependency Injection at the constructor level:

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

(For completeness sake, we made `UserRepository` implement an interface as well so that it too can now be injected into calling code).

Our code now shields us from direct implementations, making it easier to change, maintain and test. Also, while the `FindByCredentials` method might be seen by some as slightly less explicit (which I agree with), if you really think about it, you'll find that the `UserRepository` class as a whole is now more explicit. You can quickly look at the `UserRepository` constructor and gain a good understanding of *how* it achieves what it does. Yet another benefit, which we'll talk more about in a following chapter, is that constructor injection helps keep our classes cohesive (having a narrow, defined, purpose) - as having too many dependencies often means having a class that does too much.

From the above example you should be able to guess what method and property injection look like. Injecting into a method is useful when only that method has a specific dependency (though it should be used sparingly as it's generally not a great sign about the cohesiveness between the method and its class). Property injection is great for optional dependencies (which is also quite rare). Property injection is also useful for internal framework code when you don't want or need inheriting classes having to expose complex constructors.

### Dependency Injection Frameworks ###
In the communities where DI is a common pattern, DI frameworks are readily available and talked about; thus we'll keep this rather brief. What you need to know is that the DI example we looked at above, when manually done, can add a noticeable amount of overhead to our coding. If, from user input to external service (database, web service, etc.), our code is roughly 4-5 levels deep, and your average class might have a dependency on 1-3 other classes/components, then tracking and instantiating our objects isn't going to be a whole lot of fun.

This is where DI frameworks come into play. You configure them with the dependencies you want to use, and let the framework manage them handle object instantiation. In a way, you can think of them like the `new` keyword on steroids - able to figure out what parameters an object's constructor requires and how to create them (because they themselves might have dependencies which need to be resolved). This is known as auto-wiring.

Let's look at an example using [Ninject](http://ninject.org/). The first thing we do is configure our DI framework. The details of this will vary based on the framework you use, Ninject uses a fluent interface.

	private sealed class BoostrapDependencyModule : NinjectModule
	{
		public override void Load()
		{
			Bind<IUserRepository>().To<UserRepository>();
			Bind<IDataStore>().To<SqlDataStore>();
				
			//makes this a singleton
			Bind<IEncryptor>().To<Encryptor>().InSingletonScope();
		}
	}

We can now create an Ninject kernel and ask it for instances:

	var kernel = new StandardKernel(new BoostrapDependencyModule());
	var repository = kernel.Get<IUserRepository();

The DI framework will see that the constructor for `UserRepository` (the configured instance for `IUserRepository` that we are asking for) requires two dependencies which it is aware of and thus be able to create an instance for us.

Keep in mind that the goal of DI frameworks isn't to make your code dynamically pluggable. The idea isn't to be able to hot-swap your `SQLServerDataStore` with a `PostgreSQLServerDatastore`. It's simpler than that. We want to program against interfaces and have those interfaces injected where necessary. It's something we can do manually, but even simple examples can be a pain. The DI framework automates a very small, yet important, part of the process (object creation with auto-wiring).

It's hard to pass up an opportunity to complain about XML-based configuration, so...Most .NET frameworks provide both code-based (as seen above) and XML-based configuration. The benefit of code-based is that you are able to refactor as well as test your configuration. There's no advantage to XML-based configuration, though some developers will state that with XML they don't need to recompile and retest their code. I say that's crap: a change to your configuration, regardless of where it's stored, needs to go through the same QA and deployment procedures as any other code change.

### Dependency Injection Framework Anti Pattern ###
Ending our introduction on Dependency Injection with what we covered above would be a disservice. We've covered the mechanics of DI and DI Frameworks, but in focusing on the *what*, we've introduced some pretty nasty *hows*. Our `kernel` instance from the last example is thread-safe, and we could create a static class and call something like `Factory.Get<T>` everywhere in our code. As we suggested above, DI frameworks can be seen as a replacement for `new`, so that might seem a logical approach. 
	
Using our DI framework in such a way is known as the Service Locator pattern, but it is generally viewed as an anti-pattern. You want to try to limit directly using the DI framework. If you are using a modern framework, there should be hooks where the framework stops and your code starts to make this possible. For example, ASP.NET MVC 1 and 2 allows you to provide a custom controller factory which can then be used as a starting point for the dependency resolution process (version 3 has even simpler to use hooks). In fact, most DI frameworks will provide these hooks for various frameworks, such as Ninject's `NinjectHttpApplication` which you simply inherit from, tell it about your modules, and move on. As a simple check, search your solution for how many times you are importing your DI's namespace (if you are using Ninject, you could search for `using Ninject`), hopefully you won't find it in more than 4 or 5 places.

The point is that with static languages, DI should be more of a configuration/setup exercise than a coding one. You might end up calling it directly at the lowest levels, but the automatic resolution should flow from there. If you are using a framework that doesn't make this possible in all but a few cases, use a different framework.

### In This Chapter ###
In this chapter we looked at what Inversion of Control is as well as the problem we are trying to solve with it (reducing coupling). We also saw a common IoC pattern, Dependency Injection. For a lot of developers this is a different way of programming and thinking. Remember though that we do gain a lot from it: code is easier to change and refactor, classes with poor cohesion are easier to spot and tests are easier to write. 

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