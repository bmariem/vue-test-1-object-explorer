<script>

export default {
  name: 'CustomTree',
  props: ['nestedObject']
}
</script>
<template>
    <div>
        <div v-for="(val,key) in nestedObject" class="tree">
          <p v-if="typeof val === 'object'"> 
            <span>{{ key }}:</span> <CustomTree v-bind:nestedObject="val" /> 
          </p>
          <p v-else>
            <input v-model="key" > :<input v-model="nestedObject[key]" >
          </p>
        </div>
    </div>
</template> 

<style lang="css">
.tree p {
    color: #2c3e50;
    margin-left: 10px;
    border-left:1px solid #a7d9f7;
    display:flex;
    border-radius:4px;
    padding-left:6px
}
.tree p span {
  text-decoration: underline;
  margin-right: 5px;
}
</style>