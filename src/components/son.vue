<template>
    <div>
        <button :class="'i-button-size' + size" :disabled="disabled" id="btn" @click="handleClick('str')">按钮</button>
        <slot name="action"></slot>
    </div>
</template>
<script>
 // 判断参数是否是其中之一
 function oneOf (value, validList) {
   for (let i = 0; i < validList.length; i++) {
     if (value === validList[i]) {
     	return true
     }
   }
   return false;
 }
 export default {
   inheritAttrs: false,
   props: {
     
     size: {
       validator (value) {
         return oneOf(value, ['small', 'large', 'default']);
       },
       default: 'default'
     },
     disabled: {
       type: Boolean,
       default: false
     }
   },
   methods: {
    handleClick (str) {
        this.$emit('fu', str);
    }
   }
 }
</script>