<template>
    <div class="item">
           <div
            v-for="colorBox in color.inputNum"
            v-bind:key="colorBox"
            :style="{background: color.inputColor}"

          >

          </div>
          </div>
</template>    

