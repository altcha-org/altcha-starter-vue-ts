# ALTCHA Widget with Vite + Vue

This is an example Vue project using the [ALTCHA](https://altcha.org) widget.

## Overview

ALTCHA is a free, open-source, self-hosted solution designed to protect websites, APIs, and online services from spam and unwanted content. It leverages a proof-of-work mechanism and is fully GDPR compliant, as it does not use cookies, fingerprinting, or tracking of any kind.

## Get Started

To quickly get your project up and running with the ALTCHA widget, follow these steps:

1. Clone this repository and navigate to the project directory:

```sh
git clone https://github.com/altcha-org/altcha-starter-vue-ts.git
cd altcha-starter-vue-ts
```

2. Install the project dependencies:

```sh
npm install
```

3. Start the development server:

```sh
npm run dev
```

## Creating a New Project Using Vite

If you prefer to create a new project from scratch, here are the steps:

1. Create a new Vite project with Vue template:

```sh
npm create vite@latest my-vue-app -- --template vue-ts
```

2. Navigate to your project directory:

```sh
cd my-vue-app
```

3. Install the ALTCHA widget package:

```sh
npm install altcha --save
```

4. Import the `altcha` package in your project:

```javascript
// src/main.js or src/main.ts
import 'altcha';
```

5. Use the `<altcha-widget>` element in your component:

```vue
<!-- ExampleComponent.vue -->
<template>
  <div>
    <h1>My Vue App with ALTCHA</h1>
    <altcha-widget challengeurl="https://your-challenge-url.com"></altcha-widget>
  </div>
</template>

<script>
export default {
  name: 'ExampleComponent',
};
</script>
```

6. To fix issues with custom WebComponents, edit your vite.config.ts and make sure to include `isCustomElement`:

```ts
export default defineConfig({
  plugins: [vue({
    template: {
      compilerOptions: {
        isCustomElement: (tag) => tag.indexOf('-') >= 0
      }
    }
  })],
})
```

## Additional Configuration

Ensure your `challengeurl` points to the endpoint where ALTCHA's proof-of-work challenge is processed. Customize the component attributes as needed based on your specific use case.

## Conclusion

With these steps, you should have a Vue project running with the ALTCHA widget integrated. This setup helps protect your application from spam and unwanted content efficiently and compliantly. For more details, visit the [ALTCHA documentation](https://altcha.org/docs/v2).