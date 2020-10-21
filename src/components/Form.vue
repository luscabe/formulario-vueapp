<template>
  <v-container grid-list-md>
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
                v-if="field.mask"
                :is="field.component"
                :placeholder="field.placeholder"
                :items="field.items"
                v-mask="field.mask"
                :label="field.label"
                v-model="payload[field.model]"
              />
              <component
                v-else
                :is="field.component"
                :placeholder="field.placeholder"
                :items="field.items"
                :label="field.label"
                v-model="payload[field.model]"
              />
            </v-col>
          </v-row>
        </v-layout>
      </v-card-text>
      <v-card-actions>
        <v-btn text @click="sendsDataToForm">Enviar Informações</v-btn>
      </v-card-actions>
    </v-card>
  </v-container>
</template>

<script>
import { mask } from 'vue-the-mask';

export default {
  name: 'Form',
  directives: {
    mask,
  },
  data: () => ({
    payload: {},
  }),
  methods: {
    sendsDataToForm() {
      this.$emit('valores', this.payload);
    },
  },
  props: {
    form: {
      type: Object,
      default: () => [],
    },
  },
};
</script>
