## Coding Conventions ##

### Introduction ###

This document will describe a set of guidelines used in the *Elsewhere Games* .Net projects. Strict adherence to the rules are not required. Since most of these rules  

### Version Control ###

**DO** create a branch for each feature you work on.

**DON'T** add third-party dependencies to the repository if they can be retrieved using [Nuget](https://www.nuget.org/).

    nuget restore

### Automated Testing ###

**DO** accompany each class library project with a test project.

**DON'T** Strictly adhere to [TDD](http://en.wikipedia.org/wiki/Test-driven_development).  

### Code Style ###

#### `Using` Statements ####

**DO** enclose `using` statements in a region.

    #region Using
    
    using System.Collections.Generic;

    #endregion Using

**DO** group using statements further using nest regions using the top-level name.

    #region Using

    #region System
    
    using System.Collections.Generic;

    #endregion System

    #region Elsewhere

    using Elsewhere.Logging

    #endregion Elsewhere

    #endregion Using

#### Variable and Operations ####

- Use descriptive names, no abbreviations.
- When referencing a class variable, always prepend the reference with `this.`.
- [Hungarian notation](http://en.wikipedia.org/wiki/Hungarian_notation) is not allowed.

#### Interfaces ####

- Interface names shall never use the `I` prefix (see the Hungarian notation rule). They also cannot have `Interface` appended to their name. Use the same names as you use for abstract or regular classes.

