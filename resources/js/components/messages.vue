<template>
    <div class="msg_history">
        <template v-for="message in messages">
            <o-message v-if="message.incoming === false" :message="message"></o-message>
            <incoming-message v-else :message="message"></incoming-message>
        </template>
    </div>
</template>
<script>
    import OMessage from './include/outgoing-message'
    import IMessage from './include/incoming-message'
    import IncomingMessage from "./include/incoming-message";
    export default {
        components: {IncomingMessage, OMessage,IMessage},
        props:['messages']
    }
</script>
