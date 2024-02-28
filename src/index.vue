<template>
    <AppLayout2>
        <template #header>Slots are awesome</template>   
        <template v-slot:default>

            <AppButton2 @click="log">
                <Icon/>
                Hello World!
            </AppButton2>  
        </template>
        <!-- <template v-slot:footer></template> --> 
    </AppLayout2>
</template>

<script>
import AppButton2 from "./components2/AppButton2.vue"
import Icon from "./components/AppIcon.vue";
import AppLayout2 from "./components2/AppLayout2.vue";

export default{
    components:{
        AppButton2,
        Icon,
        AppLayout2
    },
    methods:{
        log(){
            console.log("works!!");
        }
    }
};
</script>