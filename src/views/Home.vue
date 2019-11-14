<template>
  <div class="home">
    <Form :form="usuario" @valores="exibirDados" />
    <Dialog :value="dialog" :info="info_formulario" @input="manipulaDialog"></Dialog>
  </div>
</template>

<script>
// @ is an alias to /src
import Form from '@/components/Form.vue';
import Dialog from '@/components/Dialog.vue';
import usuario from '../helper/usuario.json';

export default {
  name: 'home',
  components: {
    Form,
    Dialog,
  },
  data: () => ({
    usuario,
    info_formulario: {},
    dialog: false,
  }),
  methods: {
    exibirDados(value) {
      this.info_formulario = value;
      this.manipulaDialog(true);
    },
    manipulaDialog(value) {
      this.dialog = value;
    },
  },
};
</script>
