This is a small repro for https://github.com/DefinitelyTyped/DefinitelyTyped/pull/67580

## The problem

I made a test using `test.todo` of jest.
You can run by `pnpm run test` and will get the following error even we don't get any type error:

```
    Todo must be called with only a description.

      3 | });
      4 |
    > 5 | test.todo("1 + 2 is equal to 3", () => {
        |      ^
      6 |   expect(1 + 2).toBe(3);
      7 | });
      8 |

      at Object.todo (index.test.ts:5:6)
```

This is because `test.todo` will throw an error if you pass it a test callback function. [see here for the details](https://jestjs.io/docs/next/api#testtodoname)
