<template>

  <h1 class="title">Persat Challenge- Vue Js</h1>

  <div class="contenedor">

    <h3>Default Button</h3>
    <div class="button-container">
      <MyButton buttonText="Default" size="xl" />
      <MyButton buttonText="Default" size="lg" />
      <MyButton buttonText="Default" size="md" />
      <MyButton buttonText="Default" size="sm" />

    </div>

    <h3>Success Button </h3>
    <div class="button-container">
      <MyButton buttonText="Success" size="xl" class="success" :onClick="() => handleClick('Success')" />
      <MyButton buttonText="Success" size="lg" class="success" :onClick="() => handleClick('Success')" />
      <MyButton buttonText="Success" size="md" class="success" :onClick="() => handleClick('Success')" />
      <MyButton buttonText="Success" size="sm" class="success" :onClick="() => handleClick('Success')" />
    </div>
    
    <h3>Danger Button </h3>
    <div class="button-container">
      <MyButton buttonText="Danger" size="xl" class="danger" :onClick="() => handleClick('Danger')" />
      <MyButton buttonText="Danger" size="lg" class="danger" :onClick="() => handleClick('Danger')" />
      <MyButton buttonText="Danger" size="md" class="danger" :onClick="() => handleClick('Danger')" />
      <MyButton buttonText="Danger" size="sm" class="danger" :onClick="() => handleClick('Danger')" />
    </div>

    <h3>Warning Button </h3>
    <div class="button-container">
      <MyButton buttonText="Warning" size="xl" class="warning" :onClick="() => handleClick('Warning')" />
      <MyButton buttonText="Warning" size="lg" class="warning" :onClick="() => handleClick('Warning')" />
      <MyButton buttonText="Warning" size="md" class="warning" :onClick="() => handleClick('Warning')" />
      <MyButton buttonText="Warning" size="sm" class="warning" :onClick="() => handleClick('Warning')" />
    </div>

    <h3>Disabled Button </h3>
    <div class="button-container">
      <MyButton buttonText="Disabled" size="xl" disabled />
      <MyButton buttonText="Disabled" size="lg" disabled />
      <MyButton buttonText="Disabled" size="md" disabled />
      <MyButton buttonText="Disabled" size="sm" disabled />
    </div>

    <h3>Button Types </h3>
    <div class="button-container">
      <MyButton buttonText="Button" type="button" />
      <MyButton buttonText="Submit" type="submit" />
      <MyButton buttonText="Reset" type="reset" />
    </div>

  </div>

</template>

<script setup lang="ts">

import MyButton from './components/MyButton.vue'
//Métodos
const handleClick = (text: string) => {
  alert(text)
}
</script>

<style scoped>
* {
  font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}
.title{
  text-align: center;
  margin-bottom: 5px;
}

.contenedor {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center
}
.button-container{
  
  margin-bottom: 10px;
  
}
</style>