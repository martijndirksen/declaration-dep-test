# declaration-dep-test

This repository illustrates what happens when you have two dependencies with inconsistent type declarations. 

Given the example:

```javascript
const result = add(4, multiply(3, 4))
```

And the type declarations:

```typescript
add(a: number, b: number): number;
multiply(a: number, b: number): boolean;
```

The TypeScript compiler will fail to compile the code as the return type of `multiply` is incompatible with the arguments of `add`.

```
TSError: ⨯ Unable to compile TypeScript:
index.ts:5:25 - error TS2345: Argument of type 'boolean' is not assignable to parameter of type 'number'. 

5   const result = add(4, multiply(3, 4));
                          ~~~~~~~~~~~~~~
```

## How to reproduce

1. Clone the repository
2. Run `npm install`
3. Run `npm run start`
