<template>
    <!-- NOTE The width must be equal to or greater than the height of the button -->
    <button>
        <div class="background">
            <svg x="0px" y="0px" viewBox="0 0 100 100" preserveAspectRatio="xMidYMid slice" role="img">
                <polygon class="triangle" points="100,100 0,100 0,0 "/>
            </svg>
        </div>
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
$button-color: $teal;
$transition1: 800ms ease-in-out;
$transition2: 50ms linear;

.triangle{
    fill:$button-color;
}
.background{
    position: absolute;
    background-color: white;
    display: flex;
    justify-content: flex-start;
    align-items: flex-end;
    left: 0;
    bottom: 0;
    z-index: -2;
    height: 100%;
    width: 100%;
    svg{
            height: 50%;
            aspect-ratio: 1/1;
        }
}
.foreground{
    position: relative;
}

button{
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    position: relative;
    padding: 0.5rem;
    border: 0;
    background: transparent;
    z-index: 2;
    border-radius: 0.15rem;
    overflow: hidden;
    box-shadow: 0 3px 1px -2px rgba(0, 0, 0, 0.2), 0 2px 2px 0 rgba(0, 0, 0, 0.14), 0 1px 5px 0 rgba(0, 0, 0, 0.12);
    cursor: pointer;
        &::after{
            content: "";
            z-index: -1;
            position: absolute;
            right: 100%;
            top: 100%;
            width: 600%;
            aspect-ratio: 1/1;
            background-color: $button-color;
            transition: right $transition1, background-color $transition2;
            transform: rotate(45deg);
            transform-origin: top right;
        }
        &:hover{
            &::after{
                right: -100%;
            }
        }
        &:active{
            &::after{
                background-color: darken($button-color, 10%);
            }
        }
}
</style>