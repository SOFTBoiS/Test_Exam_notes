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
Sørger for du ikke breaker builds, ved at køre tests på nye commits f.eks.

Travis CI? / Jenkins?

XP practice
Automated build & testing.  
![](https://i.imgur.com/klQuIlh.png)

### Code reviews
Review ved pull-request inden det bliver skubbet ud på branchen.  
Personligt code review med 1-2 peers.  
Sikre kvalitet, kode standarder og forståelse.  
Få et objektivt syn på koden.  

## 1.5 Testing is related to ensuring higher code quality. Elaborate on what characterizes high code quality, and what makes code testable.


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
```java
var calculator = new PriceCalculator();
calculator.UpdateCurrencyRates(eur: 1.02, gbp: 1.25);
decimal price = calculator.CalculatePrice(myShoppingCart);
```  
For at fixe dette, skal man gøre currencyRate obligatorisk:  
```java
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
Siger noget om hvor kompleks en blok kode er, og hvor mange paths du skal igennem for at teste hele kodeblokken. Det udregnes ved 1 + mængden af if, elseif, while, for og switch

Eks:

```python
class Foo:
    __init__(self,a,b):
        self.a = a
        self.b = b
    
    @property
    def x(self):
        return self.a + self.b
    
```

```csharp
Foo(int a, int b, int c){
    if (a == 4) {
        if (b == 0 && c == -1) {
            a++;
        }
        while (c > 0) {
            if (b < 0) {
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

### Unit Under Test _ System Under Test_

### Unit test lifecycle(BeforeAll, AfterAll _ SetUp, TearDown)_

### Test doubles (mock, fake, stub, spy)

### Matchers(Hamcrest)

### Test Driven Development

### Dependency Injection

### Equivalence classes, boundary value analysis, equivalence partitions

## 1.8 Explain test driven development, and how it affects the development process and code quality.
### Red, Green, Refactor

### Testable code

### Maintainable code

### Equivalence partitions

### Positive, negative tests

## 1.9 Explain about test doubles. Explain how and why mocking is useful, and in what test areas.
### JMock, mocks, spies, stubs, fakes, dummies

### Dependency injection

### Interfaces, contracts

### Black-box vs white-box

## 1.10 Characterize high quality software. Explain how writing tests can increase code quality.
### Defensive programming

### Black-box development

### Interfaces, contracts

### Inversion of control

### dependency injection

### Components

## 1.11 Elaborate on dependencies in software, and how it’s related to the subject of test.
### Dependencies between layers

### System resources
adam er (glad for sin elge ven <3) hot
læse fra I/O fx.  
timer??  
Netværk
### Relations between objects

### Dependency inversion, Inversion of Control, Dependency Injection

### Mocks

## 1.12 Explain problems in test automation, and how a continuous integration tool can help.
### What is Continuous Integration?

### How can a CI help regarding tests?

### What is a regression?

### What test levels can be covered by a CI system?

## 1.13 Explain specification-based testing, and how you can be more confident that you have written a sufficient amount of tests.
### Equivalence partitioning

### Boundary value analysis

### Edge cases
Equivelance partitioning (test 17, 18, 19 fx hvis man skal være 18 år)  
Test minus tal, bogstaver osv.
### Decision tables

### Code coverage
