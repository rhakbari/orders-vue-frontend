<template>
  <v-app dark>
    <v-navigation-drawer v-model="drawer" :mini-variant="miniVariant" :clipped="clipped" fixed app>
      <v-list>
        <v-list-item v-for="(item, i) in items" :key="i" :to="item.to" router exact>
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar :clipped-left="clipped" fixed app>
      <v-toolbar-title>
        <NuxtLink to="/">
          Delivery App
        </NuxtLink>
      </v-toolbar-title>

      <v-spacer />

    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>

  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data() {
    return {
      clipped: true,
      drawer: true,
      fixed: true,
      items: [
        {
          icon: 'mdi-account-multiple',
          title: 'Customers',
          to: '/customers',
        },
        {
          icon: 'mdi-office-building',
          title: 'Customer Companies',
          to: '/customer_companies',
        },
        {
          icon: 'mdi-truck-delivery',
          title: 'Deliveries',
          to: '/deliveries',
        },
        {
          icon: 'mdi-clipboard-text-outline',
          title: 'Orders',
          to: '/orders',
        },
        {
          icon: 'mdi-format-list-bulleted',
          title: 'Order Items',
          to: '/order_items',
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js',
    }
  },
}
</script>
