# Frontend Development
TBD.

## Framework, Tools
* Framework:
  * [Vuejs](https://vuejs.org/)
  * [Nuxtjs](https://nuxtjs.org/)
* State Management:
  * [Vuex](https://vuex.vuejs.org/)
* CSS Framework:
  * [Tailwind](https://tailwindcss.com/)
  * [Vuetify](https://vuetifyjs.com/en/)
  * [Element UI](https://element.eleme.io/#/en-US)
* Template:
  * [Vue Element Admin](https://github.com/PanJiaChen/vue-element-admin)
* Component Library:
  * [Vue Date Time](https://mariomka.github.io/vue-datetime/)
  * [Autocomplete](https://www.npmjs.com/package/vue-bootstrap-typeahead)
  * [Vue Masked Input](https://www.npmjs.com/package/vue-masked-input)
* Tools:
  * [Vee-validate](https://logaretm.github.io/vee-validate/)
  * [Code Linter](https://eslint.vuejs.org/)
## Code Style Guides
* [Code Style Guides](https://vuejs.org/v2/style-guide/)
* Guideline:
  * Use camelCase for variable name
  * Use PascalCase for class name
  * Use kebab-case for css style
  * Use PascalCase for file name
  * Use snake_case for file name as variable
  * Use clear, defined name for variables. ie. don't use const a = this.processsData, instead use const processedData = this.processData
  * Function name use Verb
  * Variable name use Noun

## Best Practices References
* [VueJs](https://vuejs.org/v2/style-guide/)
* [VuePress](https://vuepress.vuejs.org/)
* [Gridsome](https://gridsome.org/)

## Dockerfile Template

### Static Hosting
- VueCLI
  ```dockerfile
  # build VueJS app
  FROM      node:10.16-alpine as build-stage
  RUN       mkdir /app
  WORKDIR   /app
  COPY      . .
  RUN       npm install --progress=false
  RUN       npm run build

  # use nginx to serve built files from previous stage
  FROM      nginx:stable-alpine as production
  COPY      --from=build-stage /app/dist /usr/share/nginx/html
  EXPOSE    80
  CMD       ["nginx", "-g", "daemon off;"]
  ```

### Server-Side Rendering
- NuxtJS
  To enable SSR, use `mode: 'universal'` and `target: 'server'` in `nuxt.config.js`.
  ```dockerfile
  FROM node:latest
  WORKDIR /app
  COPY . .

  # ENV HOST must be exactly set as 0.0.0.0 (https://nuxtjs.org/faq/host-port/)
  ENV HOST 0.0.0.0

  # ENV PORT and EXPOSE value must be equal
  ENV PORT 3000

  RUN npm install
  RUN npm run build

  EXPOSE 3000

  # run nuxt as node http server instance
  CMD [ "npm", "run", "start" ]
  ```