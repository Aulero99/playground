<template>
<div class="container">
    <div class="row">
        <div class="col-12 py-3 flex-row justify-center">
            <h1>
                Buttons
            </h1>
        </div>
    </div>
    <div class="col-12 wrap py-3 flex-row justify-around">
        <div class="button-slot">
            <ButtonSlide cta="Button" />
        </div>
        <div class="button-slot">
            <ButtonCornerSlide cta="Button" />
        </div>
        <div class="button-slot">
            <ButtonCornerSlide cta="Button" />
        </div>
        <div class="button-slot">
            <ButtonCornerSlide cta="Button" />
        </div>
        <div class="button-slot">
            <ButtonCornerSlide cta="Button" />
        </div>
        <div class="button-slot">
            <ButtonCornerSlide cta="Button" />
        </div>
    </div>
    <div class="col-12">

    </div>
</div>
</template>
  
<script>
  export default {
    props:{

    },
    setup() {
      return {
  
      }
    }
  }
</script>

<style lang="scss" scoped>
@import "../assets/scss/main.scss";
.button-container{
    width: 100%;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
}
.button-slot{
    min-width: 7rem;
    width: 10%;
    height: 5rem;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    margin: 0.5rem;
    border-radius: 0.25rem;
    padding: 0.25rem;
    box-shadow: 0 2px 4px -1px rgba(0, 0, 0, 0.2), 0 4px 5px 0 rgba(0, 0, 0, 0.14), 0 1px 10px 0 rgba(0, 0, 0, 0.12);
}
</style>