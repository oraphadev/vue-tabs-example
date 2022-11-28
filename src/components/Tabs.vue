<template>
  <div class="tabs">
    <ul>
      <li
        v-for="(tab, index) in tabs"
        :key="index"
        :class="{ active: active === tab.name }"
        @click="setActive(tab.name)"
      >
        <span>{{ tab.icon }}</span>
      </li>
    </ul>
    <div class="content">
      <div ref="content-inner" class="content-inner">
        <div
          v-for="tab in tabs"
          :key="tab.name"
          :ref="`content-${tab.name}`"
          class="item"
        >
          <h3>{{ tab.title }}</h3>
          <p>
            Lorem ipsum dolor sit amet
            consectetur adipisicing elit.
            Sit, voluptatum!
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TheTabs',
  data: () => ({
    active: 'home',
    tabs: [
      { name: 'home', icon: 'home', title: 'Home' },
      { name: 'account', icon: 'person', title: 'Meu perfil' },
      { name: 'cart', icon: 'shopping_cart', title: 'Carrinho' },
      { name: 'qr_code', icon: 'qr_code_2', title: 'QR Code' },
      { name: 'settings', icon: 'settings', title: 'Configurações' },
      { name: 'logout', icon: 'logout', title: 'Sair' },
    ],
  }),
  computed: {
    wrapper() {
      return this.$refs['content-inner']
    },
  },
  methods: {
    setActive(tabName) {
      const [tab] = this.$refs[`content-${tabName}`]
      this.active = tabName
      this.wrapper.scrollTo({
        left: tab.offsetLeft,
        behavior: 'smooth',
      })
    },
  },
}
</script>

<style scoped>
.tabs {
  background: #121214;
  border-radius: 8px;
  overflow: hidden;
  position: relative;
  width: 360px;
}

ul {
  align-items: center;
  border-bottom: 1px solid #333;
  display: flex;
  list-style: none;
  margin: 0;
  padding: 0;
  width: 100%;
}

li {
  align-items: center;
  color: #555;
  cursor: pointer;
  display: flex;
  height: 60px;
  justify-content: center;
  transition: color 0.375s;
  user-select: none;
  width: 60px;
}

li:hover {
  color: #f3f3f4;
}

li.active {
  color: #41b883;
}

.content-inner {
  align-items: center;
  display: flex;
  overflow-x: hidden;
}

.item {
  flex-shrink: 0;
  padding: 30px 20px;
  width: 100%;
}

h3 {
  color: #f3f3f4;
  margin: 0;
}

p {
  color: #555;
  margin: 12px 0 0;
}
</style>
