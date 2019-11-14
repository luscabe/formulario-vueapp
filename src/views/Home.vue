<template>
  <div class="home">
    <Form :form="usuario" />
  </div>
</template>

<script>
// @ is an alias to /src
import Form from '@/components/Form.vue';
import usuario from '../helper/usuario.json';

export default {
  name: 'home',
  components: {
    Form,
  },
  data: () => ({
    usuario,
  }),
};
</script>
