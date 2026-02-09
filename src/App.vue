<script setup>
import Header from './components/Header.vue'
import GenericContent from './components/GenericContent.vue'
import Menu from 'primevue/menu';

import { ref } from "vue";
import { useRouter } from 'vue-router';

const router = useRouter();
const items = ref([
    {
        label: 'Vilka är vi',
        icon: 'pi pi-palette',
        route: '/theming/unstyled'
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
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.jpg" width="225" height="100" />

    <div class="wrapper">
      <Header msg="Heddas ozempicesque hemsida" />
    </div>
  </header>

  <main>
    <Menu :model="items">
      <template #item="{ item, props }">
        <a v-ripple :href="item.url" :target="item.target" v-bind="props.action" style="padding-top: 5px; padding-bottom: 5px;">
            <span :class="item.icon" />
            <span>{{ item.label }}</span>
        </a>
      </template>
    </Menu>
    <GenericContent class="content"/>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
  position: fixed;
}

main {
  margin-top: 120px;
  display: flex;
}

Menu {
    margin-top: 10px;
}

.content {
  margin-left: 40px;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
