<script>
import { ref } from "vue";

export default {
  name: "Button",
  props: {
    type: {
      type: String,
      default: "primary"
    },
    label: {
      type: String,
      default: ""
    },
    iconPos: {
      type: String,
      default: "left"
    },
    showIcon: {
      type: Boolean,
      default: false
    },
    iconName: {
      type: String,
      default: "bi-arrow-right"
    },
    disabled: {
      type: Boolean,
      default: false
    }
  },
  setup(props) {
    const { type, label, iconPos, showIcon, iconName, disabled } = props;

    return {
      type,
      label,
      iconPos,
      showIcon,
      iconName,
      disabled
    };
  }
};
</script>

<template>
  <main>    
    <button class="cool-btn" :disabled="disabled"
    :class="[{ 'd-flex' : showIcon && label != '' },`cool-btn-${type}`, {'full-button-width' : showIcon && label }]"
    >

        <i
        v-if="showIcon"
        class="cool-icon" 
        :class="[
        ( label != '' ) ? `cool-icon-${iconPos}` : '',
        `cool-icon-${type}`,
        iconName,
        iconName.includes('less') ? 'icon__style' : ''
        ]" 
        >
        </i>

        <div v-if="label != ''" class="cool-btn-content" :class="[`cool-btn-content-${type}`]">
            {{label}}
        </div>

    </button>
  </main>

</template>

<style scoped>

.full-button-width{
    width: 100%;
}


.cool-btn{
  min-width: 40px;
  justify-content: center;
  border-radius: 8px;
  padding: 6px 12px 6px 12px;
}

.cool-btn-primary {
    background: #F7BA50;
    border: 1px solid #F7BA50;
}


.cool-btn-primary:hover:enabled {
    background: #F5AB2B;
    box-shadow: 0 6px 8px 0 rgb(0 0 0 / 24%), 0 12px 40px 0 rgb(0 0 0 / 19%);

}

.cool-btn-secondary {
    background: #FFFFFF;
    border: 1px solid #C75100;
}

.cool-btn-secondary:hover:enabled {
    background: none;
    box-shadow: 0 6px 8px 0 rgb(0 0 0 / 24%), 0 12px 40px 0 rgb(0 0 0 / 19%); 
}

/* .cool-btn-secondary:hover:enabled{
    background: none;
    border-color:  #C75100; 
}

.cool-btn-secondary:hover:enabled .cool-btn-content-secondary {
    color: #C75100; 
}

.cool-btn-secondary:hover:enabled .cool-icon-secondary {
    color: #C75100; 
} */

.cool-btn-content{
  font-family: 'Open Sans';
  font-weight: 600;
  font-size: 16px;
}

.cool-btn-content-primary{
    color: #0C0D0D;
}

.cool-btn-content-secondary{
    color: #C75100;
}

.cool-icon{
  width: 24px;
  height: 24px;
}

.cool-icon-left{
    margin-right: 4px;
}

.cool-icon-right{
    margin-left: 4px;
    order : 2
}

.cool-icon-primary{
    color : #0C0D0D;
}

.cool-icon-secondary{
    color: #C75100;
}

.cool-btn:disabled {
    /* border: 1px solid #999999;
    background-color: #cccccc;
    color: #666666; */
    opacity: .65
}

.icon__style{
    width: 10px;
    margin-right: 10px;
    margin-top: 2px;
}
</style>
