<template>
  <v-container grid-list-xl>
    <v-card class="pa-5">
      <v-card-title>
        {{form.title}}
      </v-card-title>
      <v-divider></v-divider>
      <v-card-text>
        <v-layout
          text-center
          wrap
        >
          <v-row>
            <v-col
              v-for="(field, index) in form.campos"
              :key="index"
              :cols="field.xsSize"
              class="py-0"
            >
              <component
                :is="field.component"
                :placeholder="field.placeholder"
                :v-mask="field.mask"
                :items="field.items"
              />
            </v-col>
          </v-row>
        </v-layout>
      </v-card-text>
    </v-card>
  </v-container>
</template>

<script>
import { mask } from 'vue-the-mask';

export default {
  name: 'HelloWorld',
  directives: {
    mask,
  },
  props: {
    form: {
      type: Object,
      default: () => [],
    },
  },
};
</script>
