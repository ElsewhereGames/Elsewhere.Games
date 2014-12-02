# Coding Conventions #

## Introduction ##

This document will describe a set of guidelines used in the *Elsewhere Games* .Net projects. The guiding principle document is to create a code-base which is easy to maintain.

## In General ##

### The conventions are not meant to be exhaustive. ###

Too many rules will make this document impossible to maintain, read, and, most importantly, follow. This document will:

- Serve as a broad guideline
- Describe conventions not common to other .Net projects  
___ 

### Any violation to the conventions to improve readability is permitted. ###

Rules are meant to be broken. Just keep the guiding principle of this document in mind, and don't get creative without consideration of the consequences.

## Version Control ##

### Create a feature branch for each feature under development. ###

When working on a feature or bug fix, always create a branch from the `develop` branch with a descriptive name.
___

### Manage third-party dependencies using *Nuget* ###

Use a `packages.config` file to specify third-party dependencies and their version numbers. Either have *Visual Studio* [resolve the dependencies for you](http://docs.nuget.org/docs/workflows/using-nuget-without-committing-packages), or call `nuget restore`.

Try to avoid putting `.dll` files in version control.
___

## Automated Testing ##

### Accompany each class library with a test project. ###

Use either *Visual Studio*'s [integrated test library](http://www.visualstudio.com/en-us/get-started/create-and-run-unit-tests-vs.aspx) or [NUnit](http://www.nunit.org/) in a separate project with tests.

### Mark each test case a unit or integration test. ###

Using test categories, mark each test as `Unit` or `Integration` test.

```csharp

[TestFixture, Category("Unit")]
public class SimpleTests
{

}

```

___

## Naming Conventions ##

### Interface names are not prepended with the letter "I" ###

This goes against most *C#* coding conventions, however, those coding conventions usually also have rules against using [Hungarian notation](http://en.wikipedia.org/wiki/Hungarian_notation). 

Also, although this will be rare, if you need to refactor an `interface` into an `abstract class`, there are many more places in which the code will need to change, leading to more places where bugs can occur. 

___