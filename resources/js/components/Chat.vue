<template>
    <div class="messaging">
        <div class="inbox_msg">
<!--            <div class="inbox_people">-->
<!--                <div class="headind_srch">-->
<!--                    <div class="recent_heading">-->
<!--                        <h4>Recent</h4>-->
<!--                    </div>-->
<!--                    <div class="srch_bar">-->
<!--                        <div class="stylish-input-group">-->
<!--                            <input type="text" class="search-bar"  placeholder="Search" >-->
<!--                        </div>-->
<!--                    </div>-->
<!--                </div>-->
<!--               <contacts :contacts="contacts"></contacts>-->
<!--            </div>-->
            <div class="mesgs">
                <messages :messages="messages"></messages>
                <div class="type_msg">
                    <div class="input_msg_write">
                        <input type="text" class="write_msg" v-model="txt" placeholder="Type a message" @keyup.enter="storeMsg"/>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import contacts from './contacts';
import Messages from "./messages";
export default {
    components:{
        Messages,
       contacts
    },
    data(){
      return {
          txt: '',
          messages: []
      }
    },
    mounted() {
        axios
            .get('/api/messages')
            .then(res => {
                this.messages = res.data.messages
            })


        window.Echo.channel('messages')
        .listen('MessageCreatedEvent', e => {
            this.messages.push(e.msg)
        })
    },
    methods:{
        storeMsg(){
            var vm = this;
            axios.post('/api/messages',{
                txt: vm.txt
            })
            .then(res => {
                this.messages.push(res.data.msg)
                this.txt = '';
            })
        }
    }
}
</script>
