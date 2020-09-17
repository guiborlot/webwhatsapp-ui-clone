<template>
  <div id="app">
    <div class="sidebar">
      <header>
        <img class="header--avatar" src="https://w3schools.com/howto/img_avatar2.png" alt="avatar"/>
        <div class="header--buttons">
          <div class="header--btn">
            <svg xmlns="http://www.w3.org/2000/svg" enable-background="new 0 0 24 24" viewBox="0 0 24 24" fill="#919191"
                 width="24px" height="24px">
              <g>
                <rect fill="none" height="24" width="24"/>
              </g>
              <g>
                <g>
                  <g>
                    <path
                        d="M11,5.08V2C6,2.5,2,6.81,2,12s4,9.5,9,10v-3.08c-3-0.48-6-3.4-6-6.92S8,5.56,11,5.08z M18.97,11H22c-0.47-5-4-8.53-9-9 v3.08C16,5.51,18.54,8,18.97,11z M13,18.92V22c5-0.47,8.53-4,9-9h-3.03C18.54,16,16,18.49,13,18.92z"/>
                  </g>
                </g>
              </g>
            </svg>
          </div>
          <div class="header--btn">
            <svg xmlns="http://www.w3.org/2000/svg" height="24" viewBox="0 0 24 24" width="24">
              <path d="M0 0h24v24H0z" fill="none"/>
              <path fill="#919191"
                    d="M20 2H4c-1.1 0-1.99.9-1.99 2L2 22l4-4h14c1.1 0 2-.9 2-2V4c0-1.1-.9-2-2-2zM6 9h12v2H6V9zm8 5H6v-2h8v2zm4-6H6V6h12v2z"/>
            </svg>
          </div>
          <div class="header--btn">
            <svg xmlns="http://www.w3.org/2000/svg" height="24" viewBox="0 0 24 24" width="24">
              <path d="M0 0h24v24H0z" fill="none"/>
              <path fill="#919191"
                    d="M12 8c1.1 0 2-.9 2-2s-.9-2-2-2-2 .9-2 2 .9 2 2 2zm0 2c-1.1 0-2 .9-2 2s.9 2 2 2 2-.9 2-2-.9-2-2-2zm0 6c-1.1 0-2 .9-2 2s.9 2 2 2 2-.9 2-2-.9-2-2-2z"/>
            </svg>
          </div>
        </div>
      </header>
      <div class="search">
        <div class="search--input">
          <svg class="search--icon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="#919191" width="18px"
               height="18px">
            <path d="M0 0h24v24H0z" fill="none"/>
            <path
                d="M15.5 14h-.79l-.28-.27C15.41 12.59 16 11.11 16 9.5 16 5.91 13.09 3 9.5 3S3 5.91 3 9.5 5.91 16 9.5 16c1.61 0 3.09-.59 4.23-1.57l.27.28v.79l5 4.99L20.49 19l-4.99-5zm-6 0C7.01 14 5 11.99 5 9.5S7.01 5 9.5 5 14 7.01 14 9.5 11.99 14 9.5 14z"/>
          </svg>
          <input type="search" placeholder="Procurar ou começar uma nova conversa">
        </div>
      </div>
      <div class="chatlist--area">
        <div class="chatlist" v-for="item in chatlist" :key="item">
          <ChatListitem/>
        </div>
      </div>

    </div>
    <div class="contentarea">
      <ChatIntro/>
    </div>
  </div>
</template>

<script>
import ChatListitem from "@/components/ChatListitem";
import ChatIntro from "@/components/ChatIntro";

export default {
  name: 'App',
  components: {
    ChatListitem,
    ChatIntro
  },
  data() {
    return {
      chatlist: [{}, {}, {}, {}, {}, {}, {}, {}, {}, {}, {}, {}, {}, {}, {}]
    }
  },
  methods: {},
  mounted() {

  }
}
</script>

<style>
* {
  box-sizing: border-box;
}

body {
  background: #D2DBDC;
  margin: 0;
  font-family: "Segoe UI", Helvetica Neue, Helvetica, Lucida Grande, Arial;
}

#app {
  display: flex;
  height: 100vh;
  background: #EDEDED;
}

.sidebar {
  width: 35%;
  max-width: 415px;
  display: flex;
  flex-direction: column;
  border-right: 1px solid #DDD;
}

header {
  height: 60px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 15px;
}

.header--avatar {
  width: 40px;
  height: 40px;
  border-radius: 20px;
  cursor: pointer;
}

.header--buttons {
  display: flex;
}

.header--btn {
  width: 40px;
  height: 40px;
  border-radius: 20px;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
}

.search--icon {
  font-size: small;
}

.search {
  background: #F6F6F6;
  border-bottom: 1px solid #EEE;
  padding: 5px 15px;
}

.search--input {
  background: #FFF;
  height: 40px;
  border-radius: 20px;
  display: flex;
  align-items: center;
  padding: 0 10px;
}

.search--input input {
  flex: 1;
  border: 0;
  outline: 0;
  background: transparent;
  margin-left: 10px;
}

.chatlist {
  background: #fff;

}

.chatlist--area{
  flex: 1;
  overflow-y: auto;
}

.chatlist--area::-webkit-scrollbar{
  width: 6px;
  height: 6px;
}

.chatlist--area::-webkit-scrollbar-thumb{
  background: rgba(0, 0, 0, 0.2);
}


.contentarea {
  flex: 1;
}
</style>
