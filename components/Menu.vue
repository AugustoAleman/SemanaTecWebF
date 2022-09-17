<template>
  <v-navigation-drawer dark color="primary" left app>
    <v-list-item>
      <v-list-item-content>
        <v-list-item-title class="text-h6"> Menú </v-list-item-title>
      </v-list-item-content>
    </v-list-item>

    <v-divider></v-divider>

    <v-list dense nav>  <!-- dense: reduce the padding of the list items -->

      <v-list-item v-for="item in items" :key="item.title" link> <!-- link: add hover and ripple effects -->
        <v-list-item-icon> <!-- icon: add an icon to the list item -->
          <v-icon>{{ item.icon }}</v-icon>
        </v-list-item-icon> <!-- icon: add an icon to the list item -->

        <v-list-item-content> <!-- content: add a title and a subtitle to the list item -->
          <v-list-item-title>
            <NuxtLink :to="item.url">{{ item.title }}</NuxtLink>
            
          </v-list-item-title>  <!-- title: add a title to the list item -->
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>
<script>
export default {  
  data() {
    return {
      items: [ // items: add a list of items to the list
        { title: 'Inicio', icon: 'mdi-home', url: '/' },
        { title: 'Tareas', icon: 'mdi-calendar', url: '/tarea/crear' },
        { title: 'Usuarios', icon: 'mdi-account', url: '/usuario/crear' },
        { title: 'Mis tareas', icon: 'mdi-book', url: '/pendientes/tareas' },
       
       
       /* { title: "Crear Usuario", url:"" },
        { title: "Crear Tarea", url: "/tarea/crear" },
        { title: "Crear Equipo", url: "/equipo/crear" },
        { title: "Consultar Equipos", url: "/equipo/consultar"},
        { title: "Consultar Tareas", url: "/tarea/consultar"}*/
      ],
    };
  },
};
</script>
<style>
.v-application a{
  color:white!important;
}
</style>
