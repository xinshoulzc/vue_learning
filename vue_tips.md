# vue_tips
## intro to vue object
Be used in `.js`
## intro to vue component
In many Vue projects, global components will be defined using `Vue.component()`, followed by `new Vue({el: '#container'})`.
Using single-file components with a `.vue` extension
In `.vue` extension file, there may be three or four parts.
```html
<template></template>
<script type="text/javascript"></script>
<style type="text/css"></style>
<customer-tag></customer-tag> <!-not necessary>
```
In script tag, there is a single vue component:
> * There must be a space before '{'.
```html
<script type="text/javascript">
    import xxx from './xxx.vue'
    export default {
        data () {
            //return parameters in this component
            return{}
        },
        components: () {
            //your children components
        }
        methods: () {

        },
        mounted: function (){
            //executed only once after this component be rendered
        }
    }
</script>
```