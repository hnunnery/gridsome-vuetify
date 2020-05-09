<template>
  <Layout>
    <v-container>
      <v-row justify="center">
        <v-col cols="12" lg="10" xl="8" px-4>
          <h1 class="custom-header mont grey--text text--darken-3 text-center mb-6 mb-md-10">About us</h1>
          <p
            class="subtitle-1 grey--text text--darken-3"
            style="line-height: 2.5em;"
          >Lorem ipsum dolor sit amet, consectetur adipisicing elit. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ad debitis assumenda sunt hic eum necessitatibus in blanditiis veritatis? Laboriosam maxime suscipit a numquam nostrum quam optio voluptates deserunt ex quasi. Error doloremque omnis animi, eligendi magni a voluptatum, vitae, consequuntur rerum illum odit fugit assumenda rem dolores inventore iste reprehenderit maxime! Iusto.</p>
        </v-col>
      </v-row>
    </v-container>
  </Layout>
</template>

<script>
export default {
  data() {
    return {
      name: "about"
    };
  },
  metaInfo: {
    title: "About us"
  }
};
</script>

