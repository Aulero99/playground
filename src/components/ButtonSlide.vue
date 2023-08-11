<template>
  <button>
    Press Me
  </button>
</template>

<style lang="scss" scoped>
@import "../assets/scss/main.scss";

// STUB Change these variables to set the parameters of the element 
$button-color: $orange;
$transition1: 300ms ease-in-out;
$transition2: 50ms linear;

button{
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    position: relative;
    padding: 0.5rem;
    border: 0;
    background: transparent;
    z-index: 1;
    border-radius: 0.15rem;
    overflow: hidden;
    box-shadow: 0 3px 1px -2px rgba(0, 0, 0, 0.2), 0 2px 2px 0 rgba(0, 0, 0, 0.14), 0 1px 5px 0 rgba(0, 0, 0, 0.12);
    cursor: pointer;
        &::before{
            content: '';
            z-index: -2;
            position: absolute;
            background-color: white;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
        }
        &::after{
            content: '';
            z-index: -1;
            position: absolute;
            top: 0;
            left: 0;
            height: 100%;
            width: 0;
            background-color: $button-color;
            transition: width $transition1, background-color $transition2;
        }
        &:hover{
            &::after{
                width: 100%;
            }
        }
        &:active{
            &::after{
                background-color: darken($button-color, 10%);
            }
        }
}
</style>