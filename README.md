# Testing best practices

# Libs:

[Jest](https://jestjs.io/) : is a delightful JavaScript Testing Framework with a focus on simplicity.
[Nyc](https://github.com/istanbuljs/nyc): track how well the unit-tests exercise the codebase

## The AAA pattern
- Arrange: includes all set up code and test data you need to simulate a test scenario.
- Act: Executes the unit test. Usually, test execution consist of one or two lines of code.
- Assert: Groups all assertions where you compare the received output with the expected output.

Code examples: 
```js
it('should resolve with "true" when block is forged by correct delegate', async () => {
    // Arrange
    const block = {
        height: 302,
        timestamp: 23450,
        generatorPublicKey: '6fb2e0882cd9d895e1e441b9f9be7f98e877aa0a16ae230ee5caceb7a1b896ae',
    };

    // Act
    const result = await dpos.verifyBlockForger(block);

    // Assert
    expect(result).toBeTrue();
});
```

# 3-Layers system

- Layer 1: Unit that you want to test, or test requirement
- Layer 2: Specific action or scenario you want to test
- Layer 3: Describe the expected result
