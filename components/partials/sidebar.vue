<template>
    <div>
         <div class="main-sidebar">
        <aside id="sidebar-wrapper">
          <div class="sidebar-brand">
            <a href="index.html">Stisla</a>
          </div>
          <div class="sidebar-brand sidebar-brand-sm">
            <a href="index.html">St</a>
          </div>
          <ul class="sidebar-menu">
            <li v-for="(menu,i) in listMenu" :key="i">
              <nuxt-link class="nav-link" :to="menu.to">
                <i :class="menu.icon"></i> <span>{{menu.name}}</span>
              </nuxt-link>
            </li>                  
          </ul>
        </aside>
      </div>
    </div>
</template>

<script>
export default {
  data() {
    return {
      listMenu: [
        {
          name: "Emit",
          icon: "fas fa-book",
          to: "/pages/index",
        },
      ],
    }
  },
}
</script>