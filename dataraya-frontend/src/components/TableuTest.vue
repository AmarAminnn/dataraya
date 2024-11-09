<template>
  <v-card outlined class="tableauPlaceholder" :id="vizId" style="position: relative">
    <h2>Tableau Test</h2>
    <noscript>
      <a :href="dashboardUrl">
        <img :alt="altText" :src="staticImage" style="border: none" />
      </a>
    </noscript>
    <object class="tableauViz" style="display: none">
      <param name="host_url" :value="hostUrl" />
      <param name="embed_code_version" value="3" />
      <param name="site_root" value="" />
      <param name="name" :value="dashboardName" />
      <param name="tabs" value="no" />
      <param name="toolbar" value="yes" />
      <param name="static_image" :value="staticImage" />
      <param name="animate_transition" value="yes" />
      <param name="display_static_image" value="yes" />
      <param name="display_spinner" value="yes" />
      <param name="display_overlay" value="yes" />
      <param name="display_count" value="yes" />
      <param name="language" value="en-US" />
    </object>
  </v-card>
</template>

<script>
export default {
  name: "TableauTest",
  props: {
    vizId: {
      type: String,
      default: "viz1731167333892",
    },
    dashboardUrl: {
      type: String,
      default:
        "https://public.tableau.com/views/stockmonitpr/Dashboard1",
    },
    altText: {
      type: String,
      default: "Dashboard 1",
    },
    hostUrl: {
      type: String,
      default: "https%3A%2F%2Fpublic.tableau.com%2F",
    },
    dashboardName: {
      type: String,
      default: "stockmonitpr/Dashboard1",
    },
    staticImage: {
      type: String,
      default:
        "https://public.tableau.com/static/images/st/stockmonitpr/Dashboard1/1.png",
    },
  },
  mounted() {
    this.loadTableau();
  },
  methods: {
    loadTableau() {
      const divElement = document.getElementById(this.vizId);
      const vizElement = divElement.getElementsByTagName("object")[0];

      if (divElement.offsetWidth > 800) {
        vizElement.style.width = "1000px";
        vizElement.style.height = "827px";
      } else if (divElement.offsetWidth > 500) {
        vizElement.style.width = "1000px";
        vizElement.style.height = "827px";
      } else {
        vizElement.style.width = "100%";
        vizElement.style.height = "727px";
      }

      const scriptElement = document.createElement("script");
      scriptElement.src = "https://public.tableau.com/javascripts/api/viz_v1.js";
      vizElement.parentNode.insertBefore(scriptElement, vizElement);
    },
  },
};
</script>

<style scoped>
.tableauPlaceholder {
  padding: 16px;
}
</style>
