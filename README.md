This is a minimal reproduction repo to see the vue-click-carousel sync bug.

See App.vue mounted hook


Comment out mounted hook lines and carousels don't sync
inspect carousels with chrome vue devtools - each carousel has asHavFor undefined despite props passed

## Project setup
```
yarn install
```

### Compiles and hot-reloads for development
```
yarn serve**
```

### Compiles and minifies for production
```
yarn build
```

### Lints and fixes files
```
yarn lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
