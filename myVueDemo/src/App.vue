<template>
<div id="app">
    <div class="circle" @touchstart="touchstart" @touchmove="touchmove" @touchend="touchend" @click="dialogVisible=true">
        asdasdasdasdasdasdasdasdas
    </div>

    <el-dialog append-to-body :visible.sync="dialogVisible" >
        <el-tabs v-model="activeName">
            <el-tab-pane label="用户管理" name="first">用户管理</el-tab-pane>
            <el-tab-pane label="配置管理" name="second">配置管理</el-tab-pane>
            <el-tab-pane label="角色管理" name="third">角色管理</el-tab-pane>
            <el-tab-pane label="定时任务补偿" name="fourth">定时任务补偿</el-tab-pane>
        </el-tabs>
    </el-dialog>
    <div class="world" v-drag>网博</div>  
    <router-view />
  
</div>
</template>

<script>
export default {
    name: 'App',
    data() {
        return {
            a: 1,

            activeName: 'second',
            dialogVisible:false,
        }
    },
    directives: {
        drag(el, bindings, vnode) {
            el.onmousemove = function (e) {
                console.log(333)

            }
            el.onmouseleave = function (e) {
                console.log(el, bindings, vnode)
            }
        }
    },
    methods: {
        // 当鼠标点击时触发，类似onclick事件
        touchstart(e) {
            console.log('touchstart')
        },
        // 当鼠标移动时触发
        touchmove(e) {
            console.log('touchmove')
        },
        touchend(e) {

            console.log('touchend')
        }
    }
}
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
