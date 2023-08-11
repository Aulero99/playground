<template>
    <!-- NOTE The width must be equal to or greater than the height of the button -->
    <button>
        <div class="background"></div>
        <div class="foreground">
            <img :src="icon" alt="ident" v-if="!cta"> 
            {{ cta }}
        </div>
    </button>
</template>
  
<script>
  export default {
    props:{
        icon: {type: String},
        cta: {type: String}
    },
    setup() {
      return {
  
      }
    }
  }
</script>

<style lang="scss" scoped>
@import "../assets/scss/main.scss";

// STUB Change these variables to set the parameters of the element 
$button-color: $red;
$button-text: white;
$transition1: 500ms ease-in-out;
$transition2: 50ms linear;

.background{
    position: absolute;
    background-color: darken($button-color, 25%);
    display: flex;
    justify-content: flex-start;
    align-items: flex-end;
    left: 0;
    bottom: 0;
    z-index: -2;
    height: 100%;
    width: 100%;
}
.foreground{
    position: relative;
}

button{
    color: $button-text;
    font-size: 1rem;
    font-weight: 600;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    position: relative;
    padding: 0.5rem;
    border: 0;
    height: 4rem;
    aspect-ratio: 6/2;
    background: transparent;
    z-index: 2;
    border-radius: 100rem;
    overflow: hidden;
    cursor: pointer;
        &::after{
            content: "";
            z-index: -1;
            position: absolute;
            right: 0;
            top: 0;
            height: 100%;
            aspect-ratio: 7/2;
            border-radius: 100rem;
            background-color: $button-color;
            transition: aspect-ratio $transition1, background-color $transition2;
        }
        &:hover{
            &::after{
                height: 100%;
                aspect-ratio: 1/1;
            }
        }
        &:active{
            &::after{
                background-color: darken($button-color, 10%);
            }
        }
}
</style>