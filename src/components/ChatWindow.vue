<template>
  <div class="chatWindow">
    <div class="chatWindow--header">
      <div class="chatWindow--headerinfo">
        <img class="chatWindow--avatar" src="https://w3schools.com/howto/img_avatar2.png" alt="">
        <div class="chatWindow--name">Guilherme Borlot</div>
      </div>
      <div class="chatWindow--headerButtons">
        <div class="chatWindow--btn">
          <svg class="search--icon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="#919191" width="18px"
               height="18px">
            <path d="M0 0h24v24H0z" fill="none"/>
            <path
                d="M15.5 14h-.79l-.28-.27C15.41 12.59 16 11.11 16 9.5 16 5.91 13.09 3 9.5 3S3 5.91 3 9.5 5.91 16 9.5 16c1.61 0 3.09-.59 4.23-1.57l.27.28v.79l5 4.99L20.49 19l-4.99-5zm-6 0C7.01 14 5 11.99 5 9.5S7.01 5 9.5 5 14 7.01 14 9.5 11.99 14 9.5 14z"/>
          </svg>
        </div>
        <div class="chatWindow--btn">
          <svg xmlns="http://www.w3.org/2000/svg" height="24" viewBox="0 0 24 24" width="24"><path d="M0 0h24v24H0z" fill="none"/><path fill="#919191" d="M16.5 6v11.5c0 2.21-1.79 4-4 4s-4-1.79-4-4V5c0-1.38 1.12-2.5 2.5-2.5s2.5 1.12 2.5 2.5v10.5c0 .55-.45 1-1 1s-1-.45-1-1V6H10v9.5c0 1.38 1.12 2.5 2.5 2.5s2.5-1.12 2.5-2.5V5c0-2.21-1.79-4-4-4S7 2.79 7 5v12.5c0 3.04 2.46 5.5 5.5 5.5s5.5-2.46 5.5-5.5V6h-1.5z"/></svg>
        </div>
        <div class="chatWindow--btn">
          <svg xmlns="http://www.w3.org/2000/svg" height="24" viewBox="0 0 24 24" width="24"><path d="M0 0h24v24H0z" fill="none"/><path fill="#919191" d="M12 8c1.1 0 2-.9 2-2s-.9-2-2-2-2 .9-2 2 .9 2 2 2zm0 2c-1.1 0-2 .9-2 2s.9 2 2 2 2-.9 2-2-.9-2-2-2zm0 6c-1.1 0-2 .9-2 2s.9 2 2 2 2-.9 2-2-.9-2-2-2z"/></svg>
        </div>
      </div>
    </div>
    <div class="chatWindow--body" v-for="item in msg" :key="item[0]">
      <MessageItem :msg="item"/>
    </div>

    <div class="chatWindow--footer">
      <div class="chatWindow--pre">
        <div class="chatWindow--btn">
          <svg xmlns="http://www.w3.org/2000/svg" height="24" viewBox="0 0 24 24" width="24"><path d="M0 0h24v24H0z" fill="none"/><path fill="#919191" d="M11.99 2C6.47 2 2 6.48 2 12s4.47 10 9.99 10C17.52 22 22 17.52 22 12S17.52 2 11.99 2zM12 20c-4.42 0-8-3.58-8-8s3.58-8 8-8 8 3.58 8 8-3.58 8-8 8zm3.5-9c.83 0 1.5-.67 1.5-1.5S16.33 8 15.5 8 14 8.67 14 9.5s.67 1.5 1.5 1.5zm-7 0c.83 0 1.5-.67 1.5-1.5S9.33 8 8.5 8 7 8.67 7 9.5 7.67 11 8.5 11zm3.5 6.5c2.33 0 4.31-1.46 5.11-3.5H6.89c.8 2.04 2.78 3.5 5.11 3.5z"/></svg>
        </div>
      </div>
      <div class="chatWindow--inputarea">
        <input class="chatWindow--input" type="text" placeholder="Digite uma mensagem">
      </div>
      <div class="chatWindow--pos">
        <div class="chatWindow--btn">
          <svg xmlns="http://www.w3.org/2000/svg" height="24" viewBox="0 0 24 24" width="24"><path d="M0 0h24v24H0z" fill="none"/><path fill="#919191" d="M2.01 21L23 12 2.01 3 2 10l15 2-15 2z"/></svg>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import MessageItem from "@/components/MessageItem";

export default {
  name: "ChatWindow",
  data(){
    return{
      msg: [{},{},{}]
    }
  },
  components:{
    MessageItem
  }
}
</script>

<style>
.chatWindow{
  display: flex;
  flex-direction: column;
  height: 100%;
}

.chatWindow--header{
  height: 60px;
  border-bottom: 1px solid #ccc;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.chatWindow--headerinfo{
  display: flex;
  align-items: center;
  cursor: pointer;
}

.chatWindow--avatar{
  width: 40px;
  height: 40px;
  border-radius: 50%;
  margin-left: 15px;
  margin-right: 15px;
}

.chatWindow--name{
  font-size: 17px;
  color: #000;
}

.chatWindow--headerButtons{
  display: flex;
  align-items: center;
  margin-right: 15px;
}

.chatWindow--btn{
  width: 40px;
  height: 40px;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
}

.chatWindow--body{
  flex: 1;
  overflow-y: auto;
  background-color: #e5ddd5;
  background-size: cover;
  background-position: center;
  background-image: url('../assets/chatWindow-background.png');
  background-attachment: fixed;
}

.chatWindow--footer{
  height: 62px;
  display: flex;
  align-items: center;
}

.chatWindow--pre{
  display: flex;
  margin: 0 15px;
}

.chatWindow--inputarea{
  flex: 1;
}

.chatWindow--input{
  width: 100%;
  height: 40px;
  border: 0;
  outline: 0;
  background: #fff;
  border-radius: 20px;
  font-size: 15px;
  color: #4a4a4a;
  padding-left: 15px;
}

.chatWindow--pos{
  display: flex;
  margin: 0 15px;
}

</style>