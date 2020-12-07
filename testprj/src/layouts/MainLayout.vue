<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="leftDrawerOpen = !leftDrawerOpen"
        />
        <q-toolbar-title>
          TO DO APP
        </q-toolbar-title>
        <div class="text=grey-10">Traffic Lights</div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      content-class="bg-grey-1"
    >
      <q-list>
        <q-item-label
          header
          style="overflow: auto;"
          class="text-grey-10"
        >
          Контакты
        </q-item-label>
        <hr>
        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>
    <q-page-container>
      <nav>
      <a href="#anchor1">JJJJJJ</a>
      <a href="#anchor2">JJJJJJ</a>
      </nav>
      <div id="cub">
        <div id="anchor1">
        <section>
        <p id="HeadText">
          Smart Traffic Lights</p>
        <p id="text">
          {{s1}} </p>
        <img id="img1" src="https://trafficlite.000webhostapp.com/images/traffic.gif" width="50%"/>
        </section>
        </div>

        <div id="anchor2">
          <p id="text2">{{s2}}</p>
        </div>
      </div>
    </q-page-container>
  </q-layout>
</template>

<style>
  #cub
  {
    width: 50%;
    height: 90%;
    background: #fafafa;
    position: absolute;
    margin-left: 25%;
    margin-right: 25%;
    margin-top: 1%;
    margin-bottom: 5%;
  }
  #img1
  {
    margin-left: 48%;
    margin-top: 6%;
  }
  #HeadText
  {
    position: absolute;
    font-size: 2.5vw;
    margin-left: 2%;
    margin-top: 6%;
    color: rgb(0, 0, 112);
  }
  #text
  {
    position: absolute;
    margin-top: 15%;
    font-size: 1vw;
    max-width: 45%;
  }
  #anchor2
  {
    position: absolute;
    margin-top: 50%;
  }
  #text2
  {
    font-size: 1vw;
  }
</style>

<script lang="ts">
import EssentialLink from 'components/EssentialLink.vue';

const linksData = [
  {
    title: 'Github',
    icon: 'code',
    link: 'https://github.com/quasarframework',
  },
  {
    title: 'Discord канал',
    icon: 'chat',
    link: 'https://discord.gg/9Cz7PQkR',
  },
  {
    title: 'Второй сайт',
    icon: 'record_voice_over',
    link: 'https://trafficlite.000webhostapp.com',
  },
  {
    title: 'ВК',
    icon: 'public',
    link: 'https://vk.com/id470428021',
  },
];

import { defineComponent, ref } from '@vue/composition-api';

export default defineComponent({
  name: 'MainLayout',
  components: { EssentialLink },
  setup() {
    const leftDrawerOpen = ref(false);
    const essentialLinks = ref(linksData);
    const s1 = ref("Светофоры с искусственным интеллектом, которые позволяют расформировать транспортный коллапс, в отличие от светофоров прошлого поколения.");
    const s2 = ref("Светофоры с искусственным интеллектом, которые позволяют расформировать транспортный коллапс, в отличие от светофоров прошлого поколения.");

    return { leftDrawerOpen, essentialLinks, s1, s2 };
  },
});
</script>
