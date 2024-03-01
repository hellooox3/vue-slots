<template>
   <AppUserList2>
        <template #secondrow="{item}">
            <a href="'tel: ' + item.phone">{{ item.phone }}</a>
            <a href="'mailto: ' + item.email">{{ item.email }}</a>
        </template>
   </AppUserList2>
</template>

<script>

import AppUserList2 from "./components2/AppUserList2.vue";

export default{
    components:{
        AppUserList2
    },
    methods:{
    
    }
};
</script>