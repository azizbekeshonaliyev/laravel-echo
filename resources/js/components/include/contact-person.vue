<template>
    <div class="chat_list">
        <div class="chat_people">
            <div class="chat_img"> <img :src="person.avatar" :alt="person.name"> </div>
            <div class="chat_ib">
                <h5>{{ person.name}} <span class="chat_date">{{ moment(person.last_mes_date,format).format('DD MMM') }}</span></h5>
                <p>{{ person.last_mes}}</p>
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        props:['person'],
        data(){
            return {
                format: 'DD.MM.YYYY'
            }
        }
    }
</script>
