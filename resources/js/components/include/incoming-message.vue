<template>
    <div class="incoming_msg">
        <div class="incoming_msg_img"> <img :src="message.avatar"> </div>
        <div class="received_msg">
            <div class="received_withd_msg">
                <p>{{  message.txt }}</p>
                <span class="time_date"> {{ moment(message.created_at).format('DD MMM HH:mm')}}</span>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    props:['message'],
    data(){
        return {
            format: 'DD.MM.YYYY HH:mm:ss'
        }
    }
}
</script>
