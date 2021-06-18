<template>
  <div class="fullscreen bg-404 text-white text-center q-pa-md container">
    <div>
      <q-toolbar-title class="text-h4">
        <q-avatar>
          <img src="../../public/imagens/study.svg" alt="Logo Cursos"/>
        </q-avatar>
        Cursos
      </q-toolbar-title>
    </div>
    <div class="flex flex-center">
      <div>
        <div style="font-size: 18vh">
          404
        </div>
        <img src="../../public/imagens/404.svg" style="width: 45%;height: 45%;" alt="" />
        <div class="text-h3" style="opacity:.4">
          Oxi! Perdesse o que aqui menino(a)!
        </div>

        <q-btn
          class="q-mt-xl"
          color="green-3"
          text-color="blue"
          unelevated
          to="/"
          label="Retornar ao início"
          no-caps
          icon="arrow_back"
        />
      </div>
    </div>
  </div>
</template>

<style type="text/css">
  .bg-404{
    background-color: #2a7ae4;
  }


</style>

<script>
export default {
  name: 'Error404'
}
</script>
