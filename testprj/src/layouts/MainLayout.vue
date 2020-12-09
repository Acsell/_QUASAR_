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
        <span id="scroll">

      <a href="#anchor1" style="text-decoration: none;">
        <div id="scroll1">
          <div id="slider1"></div>
          <div id="slider2"></div>
          <p id="s1">Header</p>
          </div>
          </a>
      <a href="#anchor2" style="text-decoration: none;">
        <div id="scroll2">
          <div id="slider1"></div>
          <div id="slider2"></div>
          <p id="s2">Content</p>
          </div>
          </a>
      <a href="#anchor3" style="text-decoration: none;">
        <div id="scroll3">
          <div id="slider1"></div>
          <div id="slider2"></div>
          <p id="s3">Folder</p>
          </div>
          </a>
        </span>
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
          <p id="text2">{{text}}{{text}}{{text}}{{text}}{{text}}{{text}}{{text}}{{text}}{{text}}{{text}}{{text}}{{text}}{{text}}{{text}}{{text}}{{text}}{{text}}{{text}}{{text}}{{text}}{{text}}{{text}}{{text}}{{text}}{{text}}{{text}}{{text}}{{text}}{{text}}{{text}}</p>
        </div>
        <div id="anchor3">
          <p id="text3">{{text2}}{{text2}}{{text2}}{{text2}}{{text2}}{{text2}}{{text2}}{{text2}}{{text2}}{{text2}}{{text2}}{{text2}}{{text2}}{{text2}}{{text2}}{{text2}}{{text2}}{{text2}}{{text2}}{{text2}}{{text2}}{{text2}}{{text2}}{{text2}}</p>
        </div>
      </div>
    </q-page-container>
  </q-layout>
</template>

<style>
  #scroll
  {
    position: fixed;
    width: 100%;
    height: 100%;
  }
  /*  */
  #scroll1
  {
    margin-left:5%;
    margin-top: 25%;
    width:6%;
    height: 3%;
    color: black;
    background: grey;
  }
  #scroll1:not(hover) div{
    transition:1s;
  } 
  #scroll1:active div
  {
    transition:0.5s;
    background:black;
    transform: translate(80px, 80px);
    transform: scale(1000) rotate(45rad);
    opacity: 10;
  } 
  #slider1
  {
    position: absolute;
    left: -5%;
    top: 0%;
    width: 1%;
    height: 1%;
    background: blue;
    transform: rotate(45rad);
    z-index: 1000;
  }
  #s1
  {
    font-size: 1vw;
  } 
  /*  */
  #scroll2{
    margin-left:5%;
    width:5%;
    height: 3%;
    color: black;
    margin-top: 1%;
    background: grey;
  }
  #scroll2:not(hover) div{
    transition:1s;
  } 
  #scroll2:active div
  {
    transition:0.5s;
    background:black;
    transform: translate(80px, 80px);
    transform: scale(1000) rotate(45rad);
    opacity: 10;
  } 
  #s2
  {
    font-size: 1vw;
  }
  #scroll3
  {
    margin-left:5%;
    width:4%;
    height: 3%;
    min-height: 5px;
    color: black;
    margin-top: 1%;
    background: grey;
  }
  #scroll3:not(hover) div{
    transition:1s;
  } 
  #scroll3:active div
  {
    transition:0.1s;
    background:black;
    transform: translate(80px, 80px);
    transform: scale(1000) rotate(45rad);
    opacity: 10;
  } 
  #s3
  {
    font-size: 1vw;
  }
  #cub
  {
    z-index: -100;
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
    margin-top: 10%;
  }
  #anchor3
  {
    margin-top: 10%;
  }
  #text2
  {
    font-size: 1vw;
  }  
  #text3
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
    const text = ref("Текст Текст Текст Текст Текст Текст Текст Текст Текст Текст Текст Текст Текст Текст Текст Текст Текст Текст Текст Текст Текст Текст Текст");
    const text2 = ref("Текст2 Текст2 Текст2 Текст2 Текст2 Текст2 Текст2 Текст2 Текст2 Текст2 Текст2 Текст2 Текст2 Текст2 Текст2 Текст2 Текст2 Текст2 Текст2 Текст2 Текст2 Текст2 Текст2");
    return { leftDrawerOpen, essentialLinks, s1, s2, text , text2};
  },
});
</script>
