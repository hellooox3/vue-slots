<template>
    <div>
        <AppButton2 @click="log">
            <Icon/>
            Hello World!
        </AppButton2>  
    </div>
</template>

<script>
import AppButton2 from "./components2/AppButton2.vue"
import Icon from "./components/AppIcon.vue";

export default{
    components:{
        AppButton2,
        Icon
    },
    methods:{
        log(){
            console.log("works!!");
        }
    }
};
</script>