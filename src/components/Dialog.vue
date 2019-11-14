<template>
  <v-dialog v-model="visibility" >
    <v-card>
      <v-card-text>
        <v-container class="pa-3">
          <v-row>
            <v-col cols="3">
              <pre>{{info}}</pre>
            </v-col>
          </v-row>
        </v-container>
      </v-card-text>
    </v-card>
  </v-dialog>
</template>

<script>
export default {
  props: {
    value: {
      type: Boolean,
      default: false,
    },
    info: {
      type: Object,
      default: () => ({}),
    },
  },
  computed: {
    visibility: {
      get() {
        return this.value;
      },
      set(value) {
        this.$emit('input', value);
      },
    },
  },
};
</script>

<style>

</style>
