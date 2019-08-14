<template>
    <div id="app">
        <b-container>
            <b-jumbotron header="Border Radius Preview">
                <RadiusPreview/>
            </b-jumbotron>
        </b-container>
    </div>
</template>

<script>
  import RadiusPreview from './components/RadiusPreview.vue';

  export default {
    name: 'app',
    components: {
      RadiusPreview,
    },
  };
</script>

<style>
</style>
