<script setup>
import Alert from "../components/Alert.vue";
</script>

<template>
  <main>

    <h6>Danger, Header, Subtext, Actions</h6>
    <Alert
    header="A short descriptive header"
    subtext="This is a paragraph of information with additional supporting detail or links to help the user understand what they should do."
    type="danger"
    :action="true"
    :icon="true"
    />

    <h6>Success, Header, Subtext, No Actions</h6>
    <Alert
    header="A short descriptive header"
    subtext="This is a paragraph of information with additional supporting detail or links to help the user understand what they should do."
    type="success"
    :icon="true"
    />

    <h6>Warning, No Header, Subtext, Actions</h6>
    <Alert
    subtext="This is a paragraph of information with additional supporting detail or links to help the user understand what they should do."
    type="warning"
    :icon="true"
    />

    <h6>Info, No Header, Subtext, No Actions</h6>
    <Alert
    header="A short descriptive header"
    type="info"
    :icon="true"
    />
  </main>

</template>

<style scoped>

</style>
