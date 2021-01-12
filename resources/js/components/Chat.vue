<template>
    <div class="messaging">
        <div class="inbox_msg">
            <div class="inbox_people">
                <div class="headind_srch">
                    <div class="recent_heading">
                        <h4>Recent</h4>
                    </div>
                    <div class="srch_bar">
                        <div class="stylish-input-group">
                            <input type="text" class="search-bar"  placeholder="Search" >
                        </div>
                    </div>
                </div>
               <contacts :contacts="contacts"></contacts>
            </div>
            <div class="mesgs">
                <messages :messages="messages"></messages>
                <div class="type_msg">
                    <div class="input_msg_write">
                        <input type="text" class="write_msg" placeholder="Type a message" />
                        <button class="msg_send_btn" type="button"><i class="fa fa-paper-plane" aria-hidden="true"></i></button>
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
          ],
          messages: [
              {
                  id:1,
                  txt: 'We work directly with our designers and suppliers',
                  date: '09-01-2021 19:00',
                  incoming: false,
              },
              {
                  id:2,
                  txt: 'We work directly with our designers and suppliers',
                  date: '09-01-2021 19:00',
                  incoming: true,
                  avatar: 'https://ptetutorials.com/images/user-profile.png'
              },
              {
                  id:4,
                  txt: 'We work directly with our designers and suppliers',
                  date: '09-01-2021 19:00',
                  incoming: false,
              },
              {
                  id:3,
                  txt: 'We work directly with our designers and suppliers',
                  date: '09-01-2021 19:00',
                  incoming: true,
                  avatar: 'https://ptetutorials.com/images/user-profile.png'
              },
          ]
      }
    },
    mounted() {
        console.log('Component mounted.')
    }
}
</script>
