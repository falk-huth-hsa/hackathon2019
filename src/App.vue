<template>
    <!-- div id="app">
        <img alt="Vue logo" src="./assets/logo.png">
        <HelloWorld msg="Welcome to Your Vue.js App"/>
        <MeetingProject/>
    </div -->
    <div id="app">
        <MeetingProject/>
    </div>
    <!-- div id="app"></div -->
    <!-- built files will be auto injected -->
</template>

<script>
    import Vue from 'vue'
    // import HelloWorld from './components/HelloWorld.vue'
    import MeetingProject from './components/MeetingProject.vue'

    Vue.config.productionTip = false

    import VueMaterial from 'vue-material'
    import 'vue-material/dist/vue-material.min.css'
    import 'vue-material/dist/theme/default.css'

    export default {
        name: 'app',
        components: {
            // HelloWorld,
            MeetingProject
        }
    }

    Vue.use(VueMaterial)

    /** new Vue({
        el: '#app',
        components: { App },
        template: '<App/>'
    }) */
</script>

<style>
    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }
</style>
