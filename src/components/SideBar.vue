<template>
  <v-navigation-drawer expand-on-hover rail>
      <v-list>
        <v-list-item
          prepend-avatar="https://randomuser.me/api/portraits/women/85.jpg"
          subtitle="sandra_a88@gmail.com"
          title="Sandra Adams"
        ></v-list-item>
      </v-list>

      <v-divider></v-divider>

      <v-list density="compact" nav>
       <v-list-item prepend-icon="mdi-image" title="My image" value="myfiles" @click="selectOption(true)" />
       <v-list-item prepend-icon="mdi-home" title="Grey" value="shared" @click="selectOption(false)"/>
       <v-list-item prepend-icon="mdi-information" title="Info" value="info" />
      </v-list>
  </v-navigation-drawer>
</template>

<script>
export default {
emits: ['selectOption'],
methods: {
  selectOption(isColor) {
    this.$emit('selectOption', isColor);
  }
}
};
</script>




