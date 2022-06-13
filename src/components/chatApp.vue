<template>
  <h1>Chat App</h1>
</template>

<script>
export default {
  name: 'chatApp',
  data() {
    return {
      items: [],
    };
  },
  sockets: {
    connect() {
      console.log('socket connected');
    },
    customEmit() {
      console.log('this method was fired by the socket server. eg: io.emit("customEmit", data)');
    },
  },
  methods: {
    clickButton(val) {
      // this.$socket.client is `socket.io-client` instance
      this.$socket.client.emit('emit_method', val);
    },
  },
};
</script>

<style></style>
