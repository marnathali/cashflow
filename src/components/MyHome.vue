<template>
  <Layout>
      <template #header>
          <Header></Header>
      </template>
  </Layout>
</template>

<script>
import Layout from './MyLayout.vue';
import Header from './MyHeader.vue';

export default {
  components: {
    Layout,
    Header,
  },
};
</script>
