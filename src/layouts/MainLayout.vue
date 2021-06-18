<template>
  <q-layout view="hHh lpR fff">

    <q-header elevated class="bg-primary text-white">
      <q-toolbar>
        <q-btn dense flat round icon="menu" @click="left = !left" />

        <q-toolbar-title class="text-h4">
          <q-avatar>
            <img src="../assets/study.svg">
          </q-avatar>
          Cursos
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-drawer show-if-above v-model="left" side="left" bordered>
      <q-list>
        <q-item-label
          header
          class="text-grey-8"
        >
          Essential Links
        </q-item-label>
        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>

    <q-footer style="background-color: #0d3b69">
      <q-toolbar>
        <p class="text-blue-2">
          Cursos - todos os direitos reservados &copy;
        </p>
      </q-toolbar>
    </q-footer>

  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink.vue'

const linksData = [
  {
    title: 'Home',
    caption: 'Inicio do app',
    icon: 'home',
    link: '/'
  },
  {
    title: 'Formações',
    caption: 'Lista dos Cursos',
    icon: 'list',
    link: 'semLink'
  },
  {
    title: 'Atividades',
    caption: 'Lista de Atividades',
    icon: 'list',
    link: 'atividade'
  },
  {
    title: 'Usuários',
    caption: 'Lista de Usuários',
    icon: 'account_circle',
    link: 'usuario'
  }
];

export default {
  name: 'MainLayout',
  components: { EssentialLink },
  data () {
    return {
      left: false,
      essentialLinks: linksData
    }
  }
}
</script>
