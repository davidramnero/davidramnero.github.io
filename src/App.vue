<script setup>
import Header from './components/Header.vue'
import GenericContent from './components/GenericContent.vue'
import Menu from 'primevue/menu';

import { ref } from "vue";
import { useRouter } from 'vue-router';
import { onMounted, onBeforeUnmount } from 'vue'

const menu = ref();
const toggle = (event) => {
  console.log('click')
    menu.value.toggle(event);
};
const router = useRouter();
const items = ref([
    {
        label: 'Vilka är vi',
        icon: 'pi pi-palette',
        command: () => {
            toggle();
        }
    },
    {
        label: 'Gå till shoppen',
        icon: 'pi pi-link',
        command: () => {
            router.push('/introduction');
        }
    },
    {
        label: 'Ta mig härifrån',
        icon: 'pi pi-home',
        url: 'https://vuejs.org/'
    }
]);

function close(e) {
  console.log('menu.value', menu.value)
}

onMounted(() => {
  document.addEventListener('click', close)
})

onBeforeUnmount(() => {
  document.removeEventListener('click', close)
})
</script>

<template>
  <header>
    <span class="wrapper">
      <img alt="Vue logo" class="logo" src="./assets/logo.jpg"/>
      <Header msg="Heddas ozempicesque hemsida" />
    </span>
  </header>

  <main>
        <div class="card flex justify-center">
        <Button type="button" icon="pi pi-ellipsis-v" @click="toggle" aria-haspopup="true" aria-controls="overlay_menu" />
        <Menu ref="menu" id="overlay_menu" :model="items" :popup="true">
          <template #item="{ item, props }">
            <a v-ripple :href="item.url" :target="item.target" v-bind="props.action" class="sidebarItem">
                <span :class="item.icon" />
                <span>{{ item.label }}</span>
            </a>
          </template>
        </Menu>
    </div>
    <GenericContent class="content"/>
  </main>
</template>

<style scoped>
header {
  display: inline-block;
  line-height: 1.5;
  position: fixed;
  width: 100%;
}

main {
  margin-top: 120px;
  display: flex;
}

.sidebar {
    margin-top: 10px;
}

.sidebarItem {
    padding-top: 10px;
    background-color: black;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 320px) {
  .logo {
    display: inline-block;
    margin: 0 0.5rem 0 0;
    width: 120px;
    height: 50px;
  }

  .wrapper {
    display: flex;
    padding-top: 0px;
    max-height: 125px;
  }
  .sidebar {
    max-width: 150px !important;
    min-width: 50px;
    width: 100%;
  }
  .sidebarItem {
    width: 120px;
    padding-top: 5px;
    padding-bottom: 5px;
  }

  .content {
    margin-left: 10px;
  }
}

@media (min-width: 1024px) {

  .content {
    margin-left: 40px;
  }

  .logo {
    display: inline-block;
    margin: 0 2rem 0 0;
    width: 225px;
    height: 100px; 
  }

  .wrapper {
    display: flex;
  }
}
</style>
