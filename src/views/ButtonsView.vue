<script setup>
import Button from "../components/Button.vue";
 
</script>

<template>
  <main> 
    <div class="d-flex mb-3">
      <div class="mb-3 mr-10 box__width">
        &nbsp;
      </div>
      <div class="mb-3 mr-10 box__width">
        <h5>Left icon</h5>
      </div>
      <div class="mb-3 mr-10 box__width">
        <h5>Right icon</h5>
      </div>
      <div class="mb-3 mr-10 box__width">
        <h5>No icon</h5>
      </div>
      <div class="mb-3 mr-10 box__width">
        <h5>Icon Only</h5>
      </div>
      <div class="mb-3 mr-10 box__width">
        <h5>Disabled</h5>
      </div>
    </div>

    <div class="d-flex mb-3">
      <div class="mb-3 mr-10 box__width">
        <h5>Primary</h5>
      </div>
      <div class="mb-3 mr-10 box__width">
        <Button
        type="primary"
        label="Action"
        showIcon="true"
        iconPos="left"
        >
        </Button>
      </div>

      <div class="mb-3 mr-10 box__width">
        <Button
        type="primary"
        label="Action"
        showIcon="true"
        iconPos="right"
        >
        </Button> 
      </div>

      <div class="mb-3 mr-10 box__width">
        <Button
        type="primary"
        label="Action"
        >
        </Button> 
      </div>

      <div class="mb-3 mr-10 box__width">
        <Button
        type="primary"
        label=""
        showIcon="true"
        >
        </Button>
      </div>

      <div class="mb-3 mr-10 box__width">
        <Button
        type="primary"
        label="Disabled"
        showIcon="false"
        :disabled="true"
        >
        </Button>
      </div>
    </div>

    <div class="d-flex">
      <div class="mb-3 mr-10 box__width">
        <h5>Secondary</h5>
      </div>
      <div class="mb-3 mr-10 box__width">
        <Button
        type="secondary"
        label="Action"
        showIcon="true"
        iconPos="left"
        iconName="fas fa-less-than">
        </Button>
      </div>

      <div class="mb-3 mr-10 box__width">
        <Button
        type="secondary"
        label="Action"
        showIcon="true"
        iconPos="right"
        >
        </Button> 
      </div>

      <div class="mb-3 mr-10 box__width">
        <Button
        type="secondary"
        label="Action"
        >
        </Button> 
      </div>

      <div class="mb-3 mr-10 box__width">
        <Button
        type="secondary"
        label=""
        showIcon="true"
        >
        </Button>
      </div>

      <div class="mb-3 mr-10 box__width">
        <Button
        type="secondary"
        label="Disabled"
        showIcon="false"
        :disabled="true"
        >
        </Button>
      </div>
    </div>

  </main>
</template>

<style scoped>

.mr-10{
  margin-right: 10px;
}

.box__width{
  width: 150px;
}
</style>
