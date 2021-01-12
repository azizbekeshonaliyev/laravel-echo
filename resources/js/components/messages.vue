<template>
    <div class="msg_history">
        <template v-for="message in messages">
            <incoming-message :message="message"></incoming-message>
        </template>
    </div>
</template>
<script>
    import OMessage from './include/outgoing-message'
    import IMessage from './include/incoming-message'
    import IncomingMessage from "./include/incoming-message";
    export default {
        components: {IncomingMessage, OMessage,IMessage},
        props:['messages'],
        data(){
            return {
                contacts: [
                    {
                        id:1,
                        name: 'Javox',
                        avatar: 'https://ptetutorials.com/images/user-profile.png',
                        last_mes: 'Test, which is a new approach to have all solutions astrology under one roof',
                        last_mes_date: '25.12.2020'
                    },
                    {
                        id:2,
                        name: 'Khan',
                        avatar: 'https://ptetutorials.com/images/user-profile.png',
                        last_mes: 'Test, which is a new approach to have all solutions astrology under one roof',
                        last_mes_date: '25.12.2020'
                    },
                    {
                        id:3,
                        name: 'Bek',
                        avatar: 'https://ptetutorials.com/images/user-profile.png',
                        last_mes: 'Test, which is a new approach to have all solutions astrology under one roof',
                        last_mes_date: '9.01.2021'
                    },
                    {
                        id:4,
                        name: 'Samandar',
                        avatar: 'https://ptetutorials.com/images/user-profile.png',
                        last_mes: 'Test, which is a new approach to have all solutions astrology under one roof',
                        last_mes_date: '25.12.2020'
                    }
                ]
            }
        }
    }
</script>
