<template>
  <div class="chatListItem" :class="{active : isActive}">
    <img class="chatListItem--avatar" :src="chatlist.image" alt="" />
    <div class="chatListItem--lines">
      <div class="chatListItem--line">
        <div class="chatListItem--name">{{chatlist.title}}</div>
        <div class="chatListItem--date">19:00</div>
      </div>
      <div class="chatListItem--line">
        <div class="chatListItem--lastMsg">
          <p>Opa, tudo bem?</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ChatListitem",
  props:{
    chatlist: Object,
    isActive: Boolean
  }
}
</script>

<style>
  .chatListItem{
    display: flex;
    cursor: pointer;
    align-items: center;
    height: 70px;
  }

  .chatListItem:hover{
    background: #f5f5f5;
  }

  .active{
    background: #ebebeb;
  }

  .chatListItem--avatar{
    width: 50px;
    height: 50px;
    border-radius: 50%;
    margin-left: 15px;
  }

  .chatListItem--lines{
    flex: 1;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    border-bottom: 1px solid #EEE;
    padding-right: 15px;
    margin-left: 15px;

    flex-wrap: wrap;
    min-width: 0;
  }

  .chatListItem--line{
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
  }

  .chatListItem--name{
    font-size: 17px;
    color: #000;
  }

  .chatListItem--date{
    font-size: 12px;
    color: #999;
  }

  .chatListItem--lastMsg{
    font-size: 14px;
    color: #999;
    display: flex;
    width: 100%;
  }

  .chatListItem--lastMsg p{
    overflow: hidden;
    white-space: nowrap;
    text-overflow: ellipsis;
    margin: 0;
  }
</style>