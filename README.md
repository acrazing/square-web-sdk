# square-web-sdk

An unofficial npm package for [Square Web Payments SDK](https://developer.squareup.com/reference/sdks/web/payments),
with TypeScript types definition.

### ⚠️ NOTE: This is an unofficial package ⚠️

Note: This is an unofficial Square Web SDK package. You may want to try the official [Square Web SDK](https://github.com/square/web-sdk), first. 

If you've already used this package, the following migration steps may help:

1. `yarn remove square-web-sdk` or `npm uninstall --save square-web-sdk`
2. `yarn add @square/web-sdk` or `npm install --save @square/web-sdk`
3. Update your code:

```
- import { loadSquare } from 'square-web-sdk';
+ import { payments, Card } from '@square/web-sdk';

  async function usageExample() {
-     await loadSquare(false /* use sandbox */);

-     const payments = Square.payments('applicationId', 'locationId');
+     const payments = await payments('applicationId', 'locationId');
-     const card: Square.Card = await payments.card();
+     const card: Card = await payments.card();
      await card.attach('#card');

      const token = await card.tokenize();
  }
```

## Install

```bash
# via npm
npm i -S square-web-sdk

# via yarn
yarn add square-web-sdk
```

## Usage

```typescript
import { loadSquare } from 'square-web-sdk';

async function usageExample() {
    await loadSquare(false /* use sandbox */);

    const payments = Square.payments('applicationId', 'locationId');
    const card: Square.Card = await payments.card();
    await card.attach('#card');

    const token = await card.tokenize();
}
```

## License

[MIT](./LICENSE)
