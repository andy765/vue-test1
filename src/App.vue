<template>
    <div>
        <button v-for="tab in tabs" v-bind:key="tab" v-bind:class="['tab-button',{active:currentTab===tab}]" v-on:click="currentTab=tab">{{tab}}</button>
            <component v-bind:is="currentTabComponent" class="tab"></component>
    </div>
</template>
<script>
import tabHome from '@/components/tabHome.vue'
import tabPosts from '@/components/tabPosts.vue'
import tabArchive from '@/components/tabArchive.vue'
export default {
    data(){
        return {
            currentTab:'Home',
            tabs:['Home','Posts','Archive']
        }
    },
    components:{
      tabHome,tabPosts,tabArchive
    }
    ,
    computed:{
        currentTabComponent:function(){
            return 'tab' + this.currentTab
        }
    }
}
</script>

