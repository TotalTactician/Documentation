# Documentation
this repository has all documents made for this project

## Code convention
1. Case Usage:
- camelCase for variables and methods.
- PascalCase for types and classes.
- UPPER_CASE_SNAKE_CASE for constants.
- If a variable is given as parameter use _camelCase.

2. When possible open and close each statement.
3. We also use defensive programming, so first validate the parameters before the main code like so:
```cs
Func(int _num)
{
   if (_num == NULL)
   {
      return;
   }
   
   *Main code*
}
```

## Definition of Done
1. The code must be compliant with the [coding conventions](https://github.com/TotalTactician/Documentation/blob/main/README.md#code-convention).
2. The code must be tested.
   - All tests succeed.
     - Unit tests.
     - Acceptance tests.
     - Functional tests.
3. The code must be peer reviewed.
4. The code must be checked into git.
5. Acceptance criteria must be fulfilled.
