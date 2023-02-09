<template>

  <div class="alert alert-dismissible fade show d-flex" :class="`alert-${type}`">
    <div class="mr-15 mt--8" v-if="icon">
      <i class="fs-20" :class="alert_icon"></i>
    </div>
     <button type="button" class="btn-close" data-bs-dismiss="alert"></button> 
    <div>
      <h6 class="alert-heading">
        {{header}}
      </h6>

      <p class="subtext"
      :style=" header == '' ? 'margin-top: -12px;' : 'margin-top: 0px;' "
      >
        {{subtext}}
      </p>
      <div class="buttons-container">
         <button v-if="action" style="margin-right: 20px;" type="button" class="btn " :class="`btn-outline-${type}`">Action</button>

         <button v-if="action" type="button" class="btn" :class="`btn-${type}`">Action</button>
          </div>
        </div>
      </div>
    
</template>

<script>

import {ref} from "vue";
import Button from './Button.vue';

export default {
  name: 'Alert',
  components:{
    Button,
  },
  props: {
    header: {
      type : String,
      default : ''
    },
    subtext: {
      type: String,
      default: ''
    },
    type: {
      type : String,
      default : 'success'
    },
    action: {
      type : Boolean,
      default:false
    },
    icon: {
      type : Boolean,
      default : true
    }
  },
  setup(props) {
    const alert_type = ref(props.type);
    const alert_icon = ref(null);
    
    if (alert_type.value === 'danger') {
      alert_icon.value = "bi-exclamation-circle-fill"
    }
    if (alert_type.value === 'success') {
      alert_icon.value = "bi-check-circle-fill"
    }
    if (alert_type.value === 'warning') {
      alert_icon.value = "bi-exclamation-triangle-fill"
    }
    if (alert_type.value === 'info') {
      alert_icon.value = "bi-info-circle-fill"
    }

    return {
      alert_type,
      alert_icon,
    }
  }
}

</script>

<style scoped>

/* .alert-dismissible .btn-close{
  top: 4px !important;
  right: -28px !important;
  padding: 0 !important;
} */

.alert-heading{
  color : #0C0D0D !important;
}

.alert-danger{
  color: #CC3123;
  background-color: #FEF5F5;
  border-color: #CC3123;
}

.alert-success{
  color: #008700;
  background-color: #F8FFF2;
  border-color: #008700;
}

.alert-warning{
  color: #DC5A00;
  background-color: #FDF3E1;
  border-color: #DC5A00;
}

.alert-info{
  color: #2C75DD;
  background-color: #F4FAFF;
  border-color: #2C75DD;
}

.btn{
  width: 110px;
  border-radius: 8px !important;
  padding: 6px 12px 6px 12px;
}

.btn-outline-danger{
    color: #CC3123;
    border-color: #CC3123;
    background-color: #ffffff;
}

.btn-outline-success{
    color: #008700;
    border-color: #008700;
    background-color: #ffffff;
}

.btn-outline-warning{
    /* color: #C75100;
    border-color: #C75100; */
    background-color: #ffffff;
}

.btn-outline-info{
    color: #C75100;
    border-color: #C75100;
    background-color: #ffffff;
}

.btn-danger{
    background-color : #CC3123;
    border-color : #CC3123;
    /* --bs-btn-disabled-bg: #CC3123;
    --bs-btn-disabled-border-color: #CC3123; */
}

.btn-success{
    background-color : #008700;
    border-color : #008700;
    /* --bs-btn-disabled-bg: #008700;
    --bs-btn-disabled-border-color: #008700; */
}

.btn-warning{
    background-color : #C75100;
    border-color : #C75100;
    --bs-btn-disabled-bg: #C75100;
    --bs-btn-disabled-border-color: #C75100;
    --bs-btn-color: #fff;
    --bs-btn-active-color: #fff;
    --bs-btn-disabled-color: #fff;
}

.btn-info{
    /* background-color : #F7BA50;
    border-color : #F7BA50;
    --bs-btn-disabled-bg: #F7BA50;
    --bs-btn-disabled-border-color: #F7BA50; */
    --bs-btn-color: #fff;
    /* --bs-btn-active-color: #fff;
    --bs-btn-disabled-color: #fff; */
}

.mr-15{
  margin-right: 15px !important;
}

.fs-20{
  font-size: 25px !important;
}

.mt--8{
  margin-top : -8px;
}

.subtext{
  color : #0C0D0D;
}

.buttons-container{
  display: flex;
}

.alert {
  position: relative;
}

.btn-close {
  position: absolute;
  top: 0px;
  right: 0px;
  text-align: center;
}

@media (max-width: 1024px){
  .buttons-container{
    flex-direction: column;
    max-width: 190px;
    gap: 10px;
  }

  .btn{
    text-align: center;
  }
}

</style>
