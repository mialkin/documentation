# xUnit.net

## Types of unit tests

xUnit.net includes support for two different major types of unit tests — *facts* and *theories*:

- **Facts** are tests which are always true. They test invariant conditions.
- **Theories** are tests which are only true for a particular set of data.

Theory example #1:

```csharp
[Theory]
[InlineData(3)]
[InlineData(5)]
[InlineData(6)]
public void MyFirstTheory(int value)
{
    Assert.True(IsOdd(value));
}

bool IsOdd(int value)
{
    return value % 2 == 1;
}
```

Example #2:

```csharp
public class BirthdayControllerUnitTests
{
    [Theory, MemberData(nameof(ActiveBirthdays))]
    public async Task List_HasActiveBirthdays(DateTime machineUtcDate, DateTime birthdayDate)
    {
        // Do the test using machineUtcDate and birthdayDate parameters
    }

    public static readonly object[][] ActiveBirthdays =
    {
        new object[] {new DateTime(2010, 1, 10, 20, 30, 0), new DateTime(1990, 10, 9)},
        new object[] {new DateTime(2010, 1, 10), new DateTime(1990, 1, 10)},
        new object[] {new DateTime(2010, 12, 31, 21, 30, 0), new DateTime(1990, 1, 1)},
    };
}
```

## Constructor and Dispose

xUnit.net [creates a new instance ↑](https://xunit.net/docs/shared-context) of the test class for every test that is run, so any code which is placed into the constructor of the test class will be run for every single test. This makes the constructor a convenient place to put reusable context setup code where you want to share the code without sharing object instances (meaning, you get a clean copy of the context object(s) for every test that is run).

For context cleanup, add the `IDisposable` interface to your test class, and put the cleanup code in the `Dispose()` method.
