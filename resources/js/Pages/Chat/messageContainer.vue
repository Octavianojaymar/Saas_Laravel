<template>
    <div class="h-96 w-full"  style= "background-color: #F7F9FB">
        <div class="h-full p-2 flex flex-col-reverse overflow-auto">
            <div v-for="(message,index) in messages" :key="index">
                <message-item :message="message"/>
            </div>
        </div>    
    </div>
</template>
<script>
    import messageItem from './messageItem.vue'
    export default{
        components:{messageItem},
        props:['messages']
    }
</script>