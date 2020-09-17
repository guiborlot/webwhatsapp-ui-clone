<template>
  <div class="chatIntro">
    <img src="https://web.whatsapp.com/img/intro-connection-light_c98cc75f2aa905314d74375a975d2cf2.jpg" alt="phone" />
    <h1>Mantenha seu celular conectado</h1>
    <h2>O WhatsApp conecta ao seu telefone para sincronizar suas mensagens. Para reduzir o uso de dados, conecte seu telefone a uma rede Wi-Fi.</h2>
  </div>
</template>

<script>
export default {
  name: "ChatIntro"
}
</script>

<style>
.chatIntro{
  background: #f8f9fa;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100%;
  border-bottom: 6px solid #4adf83;
}

.chatIntro img{
  width: 250px;
  height: auto;
}

.chatIntro h1{
  font-size: 32px;
  color: #525252;
  font-weight: normal;
  margin-top: 30px;
}

.chatIntro h2{
  font-size: 14px;
  color: #777;
  font-weight: normal;
  margin-top: 20px;
  line-height: 20px;
  text-align: center;
}
</style>