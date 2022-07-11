# 🥞 Pancake Frontend

This project is Fork of [pancake-frontend](https://github.com/pancakeswap/pancake-frontend) to show how to beoble can be integrated into Pancake-swap

## Beoble Demo Change

### package.json

```js
"dependencies": {
    // following packages added
    "@beoble/js-sdk": "./dist/packages/js-sdk",
    "@beoble/react": "./dist/packages/react",
    "@metamask/jazzicon": "^2.0.0",
    "react-icons": "^4.4.0",
    "emoji-picker-react": "^3.5.1",
    ...,
}
```

### src/pages/\_app.tsx

```js
// describing changes to integrate beoble chat module
import { Core } from '@beoble/js-sdk'
import { BeobleProvider, Chat } from '@beoble/react'
...
const DemoAppID = "2eef3eb4-db9a-46d2-b919-0a684cb87a50"
const Beoble = new Core({appId: DemoAppID})

function MyApp(props: AppProps) {
    ...
    return(...
        <Providers store={store}>
            <BeobleProvider appId={DemoAppID} Beoble={Beoble}>
            {...}
            </BeobleProvider>
        </Providers>
        ...)
    ...
}

...

const App = ({ Component, pageProps }: AppPropsWithLayout) => {
  // Use the layout defined at the page level, if available
  const Layout = Component.Layout || Fragment
  return (
    <ProductionErrorBoundary>
      <Chat />
      ...
    </ProductionErrorBoundary>
  )
}
```

## Quick Start

install dependencies using **yarn**

```sh
yarn
```

start the development server

```sh
yarn dev
```

build with production mode

```sh
yarn build

# start the application after build
yarn start
```
