<template>
    <div id="app">
        <el-container id="container">
            <vue-page-transition name="fade">
                <router-view class="view"></router-view>
            </vue-page-transition>
            <el-footer>🤍🤍🤍 Happy Birthday you beautiful girl🤍🤍🤍</el-footer>
        </el-container>
    </div>
</template>

<script>
    export default {
        name: 'App'
    }
</script>

<style>
    #app {
        font-family: Avenir, Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        height: 100vh;
        width: 100vw;
    }

    #container {
        height: 100vh;
    }

    /* Global footer #6cc7eb */
    .el-footer {
        background-color: #73d5ff;
        color: #F5F7FA;
        text-align: center;
        line-height: 60px;
        z-index: 1;
        bottom:  0;
        position: fixed;
        width: 100vw;
    }

    /* Global transition declaration*/
    .slide-fade-enter-active {
        transition: all .8s ease;
    }

    .slide-fade-leave-active {
        transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
    }

    .slide-fade-enter, .slide-fade-leave-to {
        transform: translateX(10px);
        opacity: 0;
    }

    .el-loading-spinner .el-loading-text {
        color : #618add !important;
    }

    .el-loading-spinner .path{
        stroke : #618add !important;
    }
</style>
