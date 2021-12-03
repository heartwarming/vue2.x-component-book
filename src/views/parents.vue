<template v-slot:action>
    <div>
        <h3>2.基础：Vue.js 组件的三个 API：prop、event、slot —— parents</h3>
        <son size="large" @fu="handleClick"></son>
        <!-- 注意 v-slot 只能添加在 <template> 上  -->
        <div>tian</div>
    </div>
</template>
<script>
    import son from '../components/son.vue'
    export default {
        components: { son },
        data () {
            return {
                
            }
        },
        methods: {
            handleClick(str){
              console.log(str)
            }
        }
    }
</script>