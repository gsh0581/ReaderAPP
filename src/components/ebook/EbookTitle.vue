<template>
    <div>
<transition name="slide-down">
        <div class="title-wrapper" v-show="menuVisible" >
          <div class="left">
            <span class="icon-back" @click="back"></span>
          </div>
          <div class="right">
            <div class="icon-wrapper">
              <span class="icon-shelf" ></span>
            </div>
            <div class="icon-wrapper">
              <span class="icon-cart"></span>
            </div>
            <div class="icon-wrapper">
              <span class="icon-more"></span>
            </div>
          </div>
        </div>
      </transition>
    </div>
</template>
<script>
import {ebookMixin} from '@/utils/mixin'
export default {
    props:{
        ifTitieAndMenuShow:{
            type:Boolean,
            default:false
        }
    },

    mixins:[ebookMixin],
    methods: {
      back(){
        this.$router.go(-1)
      }
    },
}
</script>
<style lang="scss" scoped>
@import "@styles/global.scss";
    .title-wrapper {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    z-index: 151;
    display: flex;
    height: px2rem(48);
    background: #fff;
    box-shadow: 0 px2rem(8) px2rem(8) rgba(0, 0, 0, 0.15);
    .left {
      flex: 0 0 px2rem(60);
      @include left;
      margin-left: px2rem(15);
    }
    .right {
      flex: 1;
      display: flex;
      justify-content: flex-end;
      .icon-wrapper {
        flex: 0 0 px2rem(40);
        @include center;
        font-size: px2rem(22);
     
      }
    }
  
  }
</style>