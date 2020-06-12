# Test Exam Questions
## 1.1 We have looked at some static analysis tools like StyleCop, PMD, FindBugs and SonarLint. Explain how static analysis can improve code quality. Explain how it helped you or could have helped you in your project.


### StyleCop, PMD, FindBugs
Static analysis is a method of debugging, which is done without executing the program. The process provides an understanding of the code structure, and can help to ensure that the code adheres to industry standards.  

Used to make your code more readable, avoid high coupling and can remove duplicate code

https://en.wikipedia.org/wiki/StyleCop
**[PMD:](https://pmd.github.io/)**   
PMD is a source code analyzer. It finds common programming flaws like unused variables, empty catch blocks, unnecessary object creation, and so forth. It supports Java, JavaScript, Salesforce.com Apex and Visualforce, PLSQL, Apache Velocity, XML, XSL.  
Additionally it includes CPD, the copy-paste-detector. CPD finds duplicated code in Java, C, C++, C#, Groovy, PHP, Ruby, Fortran, JavaScript, PLSQL, Apache Velocity, Scala, Objective C, Matlab, Python, Go, Swift and Salesforce.com Apex and Visualforce.

http://findbugs.sourceforge.net/  
FindBugs, a program which uses static analysis to look for bugs in Java code

### Linters, SonarLint
IntelliJ "Linter": https://www.jetbrains.com/help/idea/code-style-java.html  
[Linters](https://sourcelevel.io/blog/what-is-a-linter-and-why-your-team-should-use-it)

Code standard (ex correcting case of variable names, methods, etc), line length, correct amounts of whitespace between code (Depending on your Linter configuration)

[SonarLint:](https://www.sonarlint.org/)  
SonarLint is an IDE extension that helps you detect and fix quality issues as you write code. Like a spell checker, SonarLint squiggles flaws so that they can be fixed before committing code.

### Security
Static application security testing (SAST) is a static analyzing tool for locating security vulnerabilities. 

These tools can scan millions of lines of code in a matter of minutes. SAST tools automatically identify critical vulnerabilities—such as buffer overflows, SQL injection, cross-site scripting, and others—with high confidence.  

[source, synopsys.com](https://www.synopsys.com/glossary/what-is-sast.html)
Github dependency security alert warnings (outdated packages).  
Warning when installing NPM packages.  


## 1.2 Explain test levels, and what characterizes the individual levels. Then, relate to your own project.

See this as layers, cant make integration tests before you've made unit tests. Important to only test one thing per test, so if it fails, you know it can only be this one thing in the code that makes it fail (think of general troubleshooting)

![](https://i.imgur.com/ZBbSuQ6.png)


### unit testing  
Unit test: ABCDE

https://www.tutorialsteacher.com/ioc/dependency-injection
Testing only a unit of code. You should either avoid dependencies or mock them to completely isolate the unit of code.  

Unit tests are usually made by developers as they code (white box testing).
Black box with TDD?
Unit tests ensure that the building blocks of code work independently.

Test dummies are used for dependency injection.
(Code Coverage)

### integration testing
Integration test: A-B, B-C, C-D, D-E
Testing units of code together, ideally units of code you've already unit tested

[source](http://softwaretestingfundamentals.com/integration-testing/#:~:text=INTEGRATION%20TESTING%20is%20a%20level,Definition%20by%20ISTQB)

### system testing
System: A-...-E


http://softwaretestingfundamentals.com/system-testing/
https://www.guru99.com/system-testing.html#:~:text=There%20are%20more%20than%2050%20types%20of%20System%20Testing

Recovery testing  
* Hvis systemet crasher, vil dit system så recover?  

Load testing  
* Vil systemet stadig virke når der er mange requests?  

Usability testing  
* Hvor let er dit system at bruge for brugeren?  

### load testing
Vil systemet stadig virke tilfredstillende når der er mange requests?
Load: 1000000000xA-...-E

[source](https://www.guru99.com/load-testing-tutorial.html)
http://tryqa.com/what-is-load-testing-in-software/
[plugin til load testing](https://jmeter.apache.org/)

### static testing
Test af dokumneter, specifikationer, design osv.
Test uden at køre programmet.  ????

https://www.guru99.com/static-dynamic-testing.html

https://www.guru99.com/testing-review.html

### Acceptance testing
Typically done with a UI
Blackbox testing
Checking if the requirements are met from a practical perspective
Auto-Acceptance-test done with selenium

- User acceptance testing
- Operational acceptance testing
- Contractual and regulatory acceptance testing
- Alpha and beta testing

[source](http://softwaretestingfundamentals.com/acceptance-testing/#:~:text=ACCEPTANCE%20TESTING%20is%20a%20level,Definition%20by%20ISTQB)

## 1.3 Explain what kinds of test can be carried out without running any code. Explain how it can be used on non-code documents as well.
IEEE 1028 standard (Måske skriv noget om det ?)
![](https://i.imgur.com/7S9DvLd.png)

### Reviews  
* Informal Reviews  
Ingen formelle krav.  
Typisk "forfatteren" og 1-2 reviewers valgt af forfatteren.  
Hey kan du plz checke min kode?  
Kan du plz C om jeg har stavet rigtigt?  

* Walk-Through  
Forfatteren leder review processessen.  
Andre deltager stiller spørgsmål og spotter mulige problemer i forhold til udviklingsstandarden.  
Typisk få mennesker til mødet (under 10).  
**Primary objective:** find defects
**Secondary objective:** knowledge
sharing + "is my understanding right?"
e

### Technical reviews
Mødet ledes af en anden en forfatteren selv.  
Involvere ikke managers.  
3-10 mennesker.  
**Primary objective:** Find defekter.  
**Secondary objective:** Træf tekniske beslutninger, nå en general enighed.  
Til sidst skrives en rapport, med en konklusion.  

Til mødet ville man nok gennemgå tekniske dokumenter.
**Tekniske dokumenter:**  
ReadMe,  
API Documentation  
Source kode,  
Design dokumenter,  
Use cases,  
forretnings process,  
[source](https://en.wikipedia.org/wiki/Software_technical_review)

### Management reviews
Se på projektets status og resourcer(skal der bruges flere/færre folk).   
Er vi on schedule?  
Skal vi skifte scope? (større/mindre projekt)  

https://www.testeryou.com/an-overview-of-test-design-techniques/#:~:text=Management%20review%20is%20a%20static,for%20their%20adequacy%20and%20consistency.

### Inspection (Valgfri)  

En upartisk person styrer dette møde.  
3-6 person og man kunne fx review følgende dokumenter:  
![](https://i.imgur.com/sVRwwrD.png)

### Audit
Performed by external auditors.  
Auditors **HAVE** special education or certification.  
GDPR data audit.  
Verification of certificates.  
https://www.thesslstore.com/blog/gdpr-data-audit/  
Stats kontrakter.  

### Static analysis
Teste kode ude at køre det, f.eks. med tools/metoder tsom StyleCop, PMD, SAST  
**Se 1.1**
### Linters
Naming conventions, fejlcheck osv.

## 1.4 Explain test activities, and how they are related to each other. Then explain the test activities you carried out in your project.

**Se 1.2**

### Unit testing
Unit test: ABCDE

### Integration testing
Integration test: A-B, B-C, C-D, D-E  
Testing units of code together, ideally units of code you've already unit tested

### Refactoring
![](https://i.imgur.com/TDqCuVd.png)


### Maintenance
_CI_, _Code Reviews_?
Spilmester Martin

### Continuous Integration
Git - pusher til et samlet repository, gerne flere gange om dagen 

CI tools sørger for du ikke breaker builds, ved at køre tests på nye commits f.eks.

Travis CI? / Jenkins?

XP practice
Automated build & testing.  
![](https://i.imgur.com/klQuIlh.png)

### Code reviews
Review ved pull-request inden det bliver skubbet ud på branchen.  
Personligt code review med 1-2 peers.  
Sikre kvalitet, kode standarder og forståelse.  
Få et objektivt syn på koden.  

## 1.5 Testing is related to ensuring higher code quality. Elaborate on what characterizes high code quality, and what makes code 
le.


### Testable code
Low coupling high cohesion.  
Isolation  

### Names of tests
Når du tester din kode, skal du ud fra testens navn være sikker på hvad den tester.
testYourMomsDirtyUnderwearReturnsSebbeYikes


### “sufficient” tests of a method or class
Code coverage (Komme ind på alle linjer af koden)  
![](https://i.imgur.com/eYVORrU.png)

Path coverage (Komme igennem alle valide kombinationer af veje igennem koden)  


![](https://i.imgur.com/lP55O5Q.png)


### Assertions, defensive programming
assertTrue("Sebbe", "Simp"); 😥  
**Defensive programming:**  
Man programmere sin kode så godt som muligt, så den kun kan bruges til det originale formål. (Prøver at håndtere alle edge cases / invalid inputs)

### Dependency injection

Hvis du har en klasse (a) og den er afhængig af en klasse (b) skal ansvaret for at oprette b ud af klasse a for at få en lavere kobling.  
Man kan "injecte" den afhængighed ved fx at give den med som et argument i en constructor/metode eller en "setter" metode.  
Man kan derfor lettere mocke dependencies 😎

Det er anbefalet at bruge Interfaces, da man udfra dette ved hvilke metoder og felter dependencien indeholder.

https://en.wikipedia.org/wiki/Dependency_injection#Intent
## 1.6 Explain the concept of maintainable code, and how it’s related to test. Explain how to find out if a code base is maintainable.
### Maintainability
low coupling high cohesion  
TTD (hvis gjort rigtigt) sikrer, at der er tests til alt kode.  

### Product quality
Spilmester Martin

### Temporal coupling
Når et stykke kode **altid** skal køre efter et andet stykke kode.  
I dette stykke kode skal linje 3 **ALTID** udføres efter linje 2, hvilket giver chancer for fejl for andre der skal skrive dette kode.  
```java=
var calculator = new PriceCalculator();
calculator.UpdateCurrencyRates(eur: 1.02, gbp: 1.25);
decimal price = calculator.CalculatePrice(myShoppingCart);
```  
For at fixe dette, skal man gøre currencyRate obligatorisk:  
```java=
var calculator = new PriceCalculator(eur: 1.02, gbp: 1.25);
decimal price = calculator.CalculatePrice(myShoppingCart);
```
[sovs](https://enterprisecraftsmanship.com/posts/temporal-coupling-and-immutability/#:~:text=Temporal%20coupling%20is%20coupling%20that,invoked%20in%20a%20particular%20order.)

Resultatet er mere testbar kode.
### Continuous Integration
Koden er mere maintainable fordi man ved at alt der bliver skubbet op virker vælp af C.I.

Se Continuous Integration i 1.4

![](https://i.imgur.com/klQuIlh.png)

### Static Analysis
Ved at gøre brug af static analysis tools, kan du gøre koden mere læsbar og mindre repetitiv, og dermed sørge for at koden er mere maintainable.  

Èn kodestandard sørger også for at koden er mere maintainable.  

**Se 1.3**

### Dependency injection, inversion of control
Med DI flytter du kontrollen over en klasses dependency ud af selve klassen. (inversion of control)  
Dependency injection giver dig lavere coupling, dette gør din kode mere maintainable fordi de forskellige metoder kun har ansvar for sig selv.

### Low coupling, high cohesion
Low coupling = Koden er så isoleret som muligt. (Så få dependencies som muligt)  
High cohesion = Der er høj sammenhængighed i klassen (Den har et enkelt formål).

### Cyclomatic code complexity
Siger noget om hvor kompleks en blok kode er, og hvor mange paths du skal igennem for at teste hele kodeblokken. Det udregnes ved 1 + mængden af if, elseif, while, for. Og +1 for hver case i en switch

Eks:



```csharp=
Foo(int a, int b, int c){
    if (a == 4) { // 2
        if (b == 0 && c == -1) { // 3
            a++;
        }
        while (c > 0) { // 4
            if (b < 0) { // 5
                a++;
            } else {
                a++;
            }
            c--;
        }  
    }
}

```


## 1.7 Explain unit testing, and what characterizes it in contrast to other types of test.
### What and why
Forklar om Unit Tests & de forskellige test levels.  
I unit test bliver dummies brugt til dependency injections. Jo højre op i test level man kommer, jo tættere kommer man på de rigtige klasser.

Se 1.2, 1.3.  

### Unit Under Test & System Under Test (SUT)
Som ordene beskriver

### Unit test lifecycle(BeforeAll, AfterAll, SetUp, TearDown)
BeforeAll & AfterAll: metoder der bliver kørt 1 gang per testclasse (starten og slutningen) _BeforeClass, AfterClass_  
SetUp & TearDown: Metoder der bliver kørt 1 gang per test (før og efter) _BeforeEach, AfterEach._

### Test doubles (mock, fake, stub, spy)
**Dummy** Object never used. Usually just used to fill parameter requirements.  

**Stub** Hardcoded return values to call during test. 

**Spy** same as Stub. records some info. ie. how many times it was called. 

**Mock** Pre-programmed with expectations. Can expect method call exactly 1 time. Can throw exception.

**Fake** working implementation. not suitable for production (fx in-memory DB instead of real DB)

[Martin Fowler](https://martinfowler.com/bliki/TestDouble.html)

### Matchers(Hamcrest)
Mere beskrivende assertions i form af læsbarhed og mere beskrivende exceptions. Desuden mere funktionalitet:  

```java=
Instead of:
assert(x == y);
assert(x != y);

We get: 
assert_that(x, equal_to(y))
assert_that(x, is_not(equal_to(y)))
```

```java=
List<String> collection = Lists.newArrayList("ab", "cd", "ef");
assertThat(collection, contains("ab", "cd", "ef"));
```

```java=
public class HamcrestListMatcherExamples {
    @Test
    public void listShouldInitiallyBeEmpty() {
        List<Integer> list = Arrays.asList(5, 2, 4);

        assertThat(list, hasSize(3));

        // ensure the order is correct
        assertThat(list, contains(5, 2, 4));
        assertThat(list, containsInAnyOrder(2, 4, 5))
        assertThat(list, everyItem(greaterThan(1)));
    }
}
```

[source](https://www.baeldung.com/hamcrest-collections-arrays)  
[wiki](https://en.wikipedia.org/wiki/Hamcrest)  
[JUnit uses Hamcrest?](https://stackoverflow.com/questions/27256429/is-org-junit-assert-assertthat-better-than-org-hamcrest-matcherassert-assertthat)  
http://hamcrest.org/JavaHamcrest/tutorial
### Test Driven Development
![](https://i.imgur.com/Zykd2Qs.png)


### Dependency Injection
se punkt 1.5 Dependency injection
### Equivalence classes, boundary value analysis, equivalence partitions
![](https://i.imgur.com/K0loqIP.png "XD KAN DU IKKE SE XD")  
_Her ses karakter-fordeling for procent rigtige svar_  

**boundary value analysis**: Test upper, lower. f.eks -1, 0, 64,65 osv

Opdelingen heder `equivalence partitions` og opdelinger hedder `equivalence classes`  



## 1.8 Explain test driven development, and how it affects the development process and code quality.
### Red, Green, Refactor
![](https://i.imgur.com/Zykd2Qs.png)

You write your applications by writing tests to your functionality first, then write the functionality to make tests go green. 

### Testable code


Når man skriver sine tests først, skriver man kun koden man har brug for til at testen bliver grøn.  

Low coupling high cohesion.  
Isolation  


"Testable code is code that makes automated testing quick, easy, and enjoyable."
### Maintainable code
Maintainable code is code that exhibits high cohesion and low coupling. Cohesion is a measure of how related, readable and understandable code is.  

Dependency Injection.  
TDD. CI.   

Avoid / reduce technical debt  

### Equivalence partitions
![](https://i.imgur.com/K0loqIP.png "XD KAN DU IKKE SE XD jo... ;i")  
### Positive, negative tests
Test at tingene fejler. Test at tingene virker. (virker tingene som det skal)  
Test fejlhåndtering (defensive programing)

## 1.9 Explain about test doubles. Explain how and why mocking is useful, and in what test areas.

### JMock, mocks, spies, stubs, fakes, dummies

**JMock** Library for java til at lave mock-objekter.

```java=
import org.jmock.Mockery;
import org.jmock.Expectations;

public class PublisherTest extends TestCase {
    Mockery context = new Mockery();

    public void testOneSubscriberReceivesAMessage() {
        // set up
        final Subscriber subscriber = context.mock(Subscriber.class);

        Publisher publisher = new Publisher();
        publisher.add(subscriber);
        
        final String message = "message";
        
        // expectations
        context.checking(new Expectations() {{
            oneOf (subscriber).receive(message);
        }});

        // execute
        publisher.publish(message);
        
        // verify
        context.assertIsSatisfied();
    }
}
```

**Dummy** Object never used. Usually just used to fill parameter requirements.  
Usecase: **UNIT TESTING**

**Stub** Hardcoded return values to call during test. 
Usecase: **Unit testing, integration test**

**Spy** same as Stub. records some info. ie. how many times it was called. 
Usecase: ****

**Mock** Pre-programmed with expectations. Can expect method call exactly 1 time. Can throw exception.
Usecase: ****

**Fake** working implementation. not suitable for production (fx in-memory DB instead of real DB)
Usecase: **Integration, System testing**  

[Martin Fowler](https://martinfowler.com/bliki/TestDouble.html)

### Dependency injection
_Fra 1.5_

Hvis du har en klasse (a) og den er afhængig af en klasse (b) skal ansvaret for at oprette b ud af klasse a for at få en lavere kobling.  
Man kan "injecte" den afhængighed ved fx at give den med som et argument i en constructor/metode eller en "setter" metode.  
Man kan derfor lettere mocke dependencies 😎

Det er anbefalet at bruge Interfaces, da man udfra dette ved hvilke metoder og felter dependencien indeholder.

### Interfaces, contracts
Et **interface** sætter regler for klasser for hvilke metoder de *skal* indeholde. I TTD bliver interfaces implementeret når man skal lave test doubles så de stemmer overens med de rigtige klasser.  

En **kontrakt** beskriver systemets kriterier. Udfra dette ved alle udviklere hvad systemet skal kunne og hvordan tingene skal arbejde sammen, hvilket er en fordel hvis projektet er fordelt over flere teams.  

### Black-box vs white-box

![](https://i.imgur.com/vEinXhL.png)

Unit Testing: Mostly white-box, except for TDD  
Acceptance Testing: Black-box  

## 1.10 Characterize high quality software. Explain how writing tests can increase code quality.
### Defensive programming
Man programmere sin kode så godt som muligt, så den kun kan bruges til det originale formål. (Prøver at håndtere alle edge cases / invalid inputs)

### Black-box development
 
Spillemester Martin (Lørdag?)

### Interfaces, contracts
Et **interface** sætter regler for klasser for hvilke metoder de *skal* indeholde. I TTD bliver interfaces implementeret når man skal lave test doubles så de stemmer overens med de rigtige klasser.  

En **kontrakt** beskriver systemets kriterier. Udfra dette ved alle udviklere hvad systemet skal kunne og hvordan tingene skal arbejde sammen, hvilket er en fordel hvis projektet er fordelt over flere teams.  

### Inversion of control
Med DI flytter du kontrollen over en klasses dependency ud af selve klassen. (inversion of control)  
Dependency injection giver dig lavere coupling, dette gør din kode mere maintainable fordi de forskellige metoder kun har ansvar for sig selv.

### dependency injection
Se ovenfor ↑  
Hvis du har en klasse (a) og den er afhængig af en klasse (b) skal ansvaret for at oprette b ud af klasse a for at få en lavere kobling.  
Man kan "injecte" den afhængighed ved fx at give den med som et argument i en constructor/metode eller en "setter" metode.  
Man kan derfor lettere mocke dependencies 😎

### Components

![](https://i.imgur.com/EIWE1z6.png)
[ref](https://www.softwaretestinghelp.com/what-is-component-testing-or-module-testing/)

A component is the lowest unit of any application. Component testing = Unit Testing

The main objective of component testing is to verify the input/output behavior of the test object. It ensures that the test object’s functionality is working correctly and completely fine as per the desired specification.

## 1.11 Elaborate on dependencies in software, and how it’s related to the subject of test.

### Dependencies between layers
Man skal undgå at have dependencies mellem lagene, for at få low coupling.  
Flyt tingene ud ved hjælp af dependency injection :+1: 


### System resources
System resources = 👎 De er ikke consistent så de er *besværligt* at teste.  
Mock dem istedet.


læse fra I/O fx.  
timer??  
Netværk
### Relations between objects
Højere relationer mellem objekter gør det sværere at teste, refactorere og vedligeholde - derfor skal man prøve at få så lav kobling som muligt.


### Dependency inversion, Inversion of Control, Dependency Injection
Med DI flytter du kontrollen over en klasses dependency ud af selve klassen. (inversion of control)  
Dependency injection giver dig lavere coupling, dette gør din kode mere maintainable fordi de forskellige metoder kun har ansvar for sig selv.

Spilmester Martin

![](https://i.imgur.com/7cH3hpA.png)


### Mocks
**Mock** is pre-programmed with expectations. Can expect method call exactly 1 time. Can throw exception.  
By having dependencies injected you can mock it. By mocking you can isolate the component which has a dependency, thus making a proper unit test


## 1.12 Explain problems in test automation, and how a continuous integration tool can help.
### What is Continuous Integration?

Continuous integration (CI) is the practice of merging all developers' working copies to a shared mainline several times a day.

Git - pusher til et samlet repository, gerne flere gange om dagen


![](https://i.imgur.com/klQuIlh.png)

### How can a CI help regarding tests?
CI tools sørger for du ikke breaker builds, ved at køre tests på nye commits f.eks.
### What is a regression?
En regression er en bug der får en funktion til at stoppe med at virke, efter ændringer i koden.  
[source](https://en.wikipedia.org/wiki/Software_regression)

Regression testing is rerunning your tests to see if earlier tested code still works

### What test levels can be covered by a CI system?


All levels of tests except user acceptance test  
unit  
integration  
load 😳  
Acceptance testing

Not Static Testing  
Not usability  
System tests omitted since there are 50 different variations of system tests 

## 1.13 Explain specification-based testing, and how you can be more confident that you have written a sufficient amount of tests.
Specification-based testing is same as black box testing. You test the system without knowing the internals of the system.   

### Equivalence partitioning
If a test can require ranges of answers, equivalence partitioning can help you making sure you have made enough tests for a component. By having covered all partition classes you have covered all code. 

Med equivalence partitioning vil du ud fra fysisk information se hvor stor en procentdel af mulighederne man rammer.  
Hvorimod, med code coverage kan du kun se hvor mange du rammer af hvad du har i koden.  

![](https://i.imgur.com/K0loqIP.png "XD KAN DU IKKE SE XD jo... ;i")  

### Boundary value analysis

Test upper, lower. f.eks -1, 0, 64,65 osv

* Minimum
* Just above the minimum
* A nominal value
* Just below the maximum
* Maximum

![](https://i.imgur.com/C2ax4Db.png)

[source](https://www.guru99.com/equivalence-partitioning-boundary-value-analysis.html)

### Edge cases
Test minus tal, bogstaver osv.

Test fejlhåndtering (defensive programing)


### Decision tables
Formuler kompleks foretningslogik med en simpel tabe.  
Den viser om alle "conditions" er opfyldt, eller om man har glemt nogle.  
Bliver brugt til at teste systemet for forskellige input kombinationer. (Path coverage uden for koden)
![](https://i.imgur.com/K3pOyPa.png)
[source](https://www.guru99.com/decision-table-testing.html)  

### Code coverage

Code coverage (Komme ind på alle linjer af koden)  
![](https://i.imgur.com/eYVORrU.png)

Path coverage (Komme igennem alle valide kombinationer af veje igennem koden)  
![](https://i.imgur.com/lP55O5Q.png)
___

![](https://i.imgur.com/pjfZOim.png)

