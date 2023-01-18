<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>
<template>
  <div id="chatgalery-all">
    <router-link :to="`/${chat.username}`" v-for="chat in chats" :vbind="chat.name" :key="chat.name" :class="`chatgalery-chat ${getClass(chat.username)}`">
      <div class="chatgalery-chats-name">
        <b v-if="chat.unread">{{ chat.name }}</b>
        <div v-else>{{ chat.name }}</div>
      </div>
      <div class="chatgalery-chats-lastmsg">
        <b v-if="chat.unread">{{ chat.last_msg }}</b>
        <div v-else>{{ chat.last_msg }}</div>
      </div>
    </router-link>
  </div>
</template>

<style>
#chatgalery-all {
  width: fit-content;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  overflow-x: scroll;
}

.chatgalery-chat {
  height: 70%;
  border: 1px solid #ffffff77;
  width: 15vw;
  border-radius: 2vh;
  margin: 1vw;
  /* box-shadow: 0 0 2vh #fff; */
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;
  cursor: pointer;
}
.chatgalery-chat:hover {
  box-shadow: 0 0 1vh #fff;
}

.chatgalery-chats-name {
  font-size: 3vh;
  margin-top: 5%;
}

.chatgalery-chats-lastmsg {
  margin-top: 5%;
}

.chatgalery-current-chat {
  border: 2px solid aqua;
}

</style>

<script>
export default {
  data() {
    return {
      chats: Object,
      currentChat: String
    }
  },
  methods: {
    getClass(username) {
      if (username == this.$route.params.username) {
        return 'chatgalery-current-chat';
      } else {
        return 'chatgalery-not-current-chat';
      }
    }
  },
  mounted() {
    this.chats = [
      {
        "username" : "maxmuster",
        "name" : "Max Muster",
        "last_msg" : "tolle testnachricht",
        "unread" : false
      },
      {
        "username" : "maxmeier",
        "name" : "Max Meier",
        "last_msg" : "tollere testnachricht",
        "unread" : false
      },
      {
        "username" : "maxmüller",
        "name" : "Max Müller",
        "last_msg" : "tollste testnachricht",
        "unread" : true
      },
      {
        "username" : "maxmeier",
        "name" : "Max Meier",
        "last_msg" : "tollere testnachricht",
        "unread" : false
      },
      {
        "username" : "maxmeier",
        "name" : "Max Meier",
        "last_msg" : "tollere testnachricht",
        "unread" : false
      },
      {
        "username" : "maxmeier",
        "name" : "Max Meier",
        "last_msg" : "tollere testnachricht",
        "unread" : false
      },
      {
        "username" : "maxmeier",
        "name" : "Max Meier",
        "last_msg" : "tollere testnachricht",
        "unread" : false
      },
      {
        "username" : "maxmeier",
        "name" : "Max Meier",
        "last_msg" : "tollere testnachricht",
        "unread" : false
      },
      {
        "username" : "maxmeier",
        "name" : "Max Meier",
        "last_msg" : "tollere testnachricht",
        "unread" : false
      },
      {
        "username" : "maxmeier",
        "name" : "Max Meier",
        "last_msg" : "tollere testnachricht",
        "unread" : false
      }
    ]
    this.currentChat = this.$route.params.username;
  }
}
</script>