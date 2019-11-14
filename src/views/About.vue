<template>
  <div class="about">
    <Form :form="curso" />
  </div>
</template>
<script>
import Form from '../components/Form.vue';
import curso from '../helper/curso.json';

export default {
  name: 'FormularioCurso',
  components: {
    Form,
  },
  data: () => ({
    curso,
  }),
};
</script>
