# Create project

```
composer create-project --prefer-dist laravel/laravel:^9.0 laravel9-vue-axample
cd laravel9-vue-axample
```

# npm install

```
npm install
npm install vue@next vue-loader@next
npm i @vitejs/plugin-vue --save-dev
```

# Edit vite.config.js


```
import { defineConfig } from 'vite';
import laravel from 'laravel-vite-plugin';
import vue from '@vitejs/plugin-vue'

export default defineConfig({
    plugins: [
        vue(),
        laravel({
            input: ['resources/css/app.css', 'resources/js/app.js'],
            refresh: true,
        }),
    ],
});
```

# Edit resouces/js/app.js

```
import './bootstrap';
import '../css/app.css';
import {createApp} from 'vue'
import App from './App.vue'
createApp(App).mount("#app")
```

# Create resources/js/App.vue

```vue
<template>
  <div class="page">
    <p>{{ counter }}</p>
    <button @click="counter += 1">
      click!
    </button>
  </div>
 </template>

 <script>
 export default {
  data () {
    return {
      counter: 0,
    }
  },
 }
 </script>
```

# Edit resources/views/welcome.blade.php

```html
<!DOCTYPE html>
  <html>
    <head>
      <meta charset="utf-8">
       <title>Hello</title>
      @vite('resources/css/app.css')
    </head>
    <body>
      <div id="app"></div>
      @vite('resources/js/app.js')
    </body>
</html>
```

# Serve

```
npm run dev
```

```
php artisan serve
```


# Access on browser

http://127.0.0.1:8000/

<img width="424" alt="image" src="https://user-images.githubusercontent.com/13635059/208239229-abbea573-5f6a-4b67-8a30-03d1f369d876.png">
