<template>
    <div>
        <h2>{{msg}}</h2>
        <hr/>
        <h3>{{$store.state.count}}-{{count}}</h3>
        <p>
            <button @click="$store.commit('add')">+</button>
            <button @click="$store.commit('reduce')">-</button>
        </p>
    </div>
</template>
<script>
    import store from '@/vuex/store'
    import {mapState} from 'vuex';
    export default{
        data(){
            return{
                msg:'Hello Vuex',
            }
        },
        /* computed: {
            count(){
                return this.$store.state.count; 
            }  
        }, */
        /* computed:mapState({
            count:state=>state.count
        }), */
       /*  computed:mapState(['count']), */
        computed:mapState({
            count:function(state){
                return state.count;
            }
        }),
        store
    }
</script>