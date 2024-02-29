<template>
    <section>
        <slot name="title">Users</slot>
        <ul class="userlist">
            <li v-for="item in data.results" :key="item.email">
                <div>
                    <img 
                    width="48"
                    height="48"
                    :src="item.picture.large" 
                    :alt="item.name.first + '' + item.name.last"
                    />
                    <div>
                        <div>{{ item.name.first }}</div>
                        <slot></slot>
                        {{ secondrow(item) }}
                    </div>
                    
                </div>
            </li>
        </ul>
    </section>
</template>


<script>
export default{
    data(){
        return{
            data:undefined,
            error:undefined
        };
    },
    props:{
        secondrow:{
            type:Function,
            default:()=>{}
        }
    },
    mounted() {
    this.load();
  },
    components:{

    },
    methods:{
        async load(){
            try{
                setTimeout(async() => {
                    const response = await fetch("https://randomuser.me/api/?results=5");
                    const json = await response.json();
                    this.data = json;
                    return response;
                },1000);
            }catch(error){
                this.error = error;
                return error;
            }
        }
    }
}
</script>

<style scoped>
.userlist {
  margin: 10px;
}
.userlist img {
  border-radius: 50%;
  margin-right: 1rem;
}

.userlist li + li {
  margin-top: 10px;
}

.userlist li > div {
  display: flex;
  align-items: center;
}

.userlist li div div {
  flex: 1;
}
</style>