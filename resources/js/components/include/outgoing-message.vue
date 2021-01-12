<template>
    <div class="outgoing_msg">
        <div class="sent_msg">
            <p>{{  message.txt }}</p>
            <span class="time_date"> {{ moment(message.date,format).format('DD MMM')}}</span>
        </div>
    </div>
</template>
<script>
    export default {
        props: ['message'],
        data(){
            return {
                format: 'DD.MM.YYYY HH:mm'
            }
        }
    }
</script>
