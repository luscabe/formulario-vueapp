<template>
  <div class="about">
    <Form :form="curso" @valores="exibirDados" />
    <Dialog :value="dialog" :info="info_formulario" @input="manipulaDialog"></Dialog>
  </div>
</template>
<script>
import Form from '../components/Form.vue';
import Dialog from '../components/Dialog.vue';

import curso from '../helper/curso.json';

export default {
  name: 'FormularioCurso',
  methods: {
    exibirDados(value) {
      this.info_formulario = value;
      this.manipulaDialog(true);
    },
    manipulaDialog(value) {
      this.dialog = value;
    },
  },
  components: {
    Form,
    Dialog,
  },
  data: () => ({
    curso,
    info_formulario: {},
    dialog: false,
  }),
};
</script>
