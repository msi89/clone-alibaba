<template>
    <div class="section">
      <div class="pub">
        <div class="container">
           <div class="counter">
             <div class="title">WEEKLY DEALS</div>
             <button class="btn_day">{{ dayStr }}</button>
             <button class="t-h">{{ hourStr }}</button>
             <span>:</span>
             <button class="t-m">{{ minuteStr }}</button>
             <span>:</span>
             <button class="t-s">{{ secondStr }}</button>
           </div>
           <div class="nav">
             <a href="">Top deals from 30% off</a>
             <a href=""><i class="far fa-check-circle"></i>Selected Suppliers</a>
           </div>
        </div>
      </div>
      <div class="container">
          <h1>welcome</h1>
          <div class="product-list">
            <a href="" class="product-card" v-for="(art,a) in 20" :key="a">
              <div class="image-content">
                <img :src="getImage(art)" alt="" class="product-img">
              </div>
              <div class="product-info" >
                <div class="price">
                  $4.24 - $5.94
                  <span>
                    <span class="price-cut-line">/</span>
                    <span class="price-unit">Pieces</span>
                  </span>
                </div>
                <div class="origin-price-and-discount">
                  <span class="origin-price">$8.48 - $11.89</span>
                  <span class="discount">- 50%</span>
                </div>
                <div class="moq">
                  <span class="moq-label">Min.Order:</span>
                  2 Pieces
                </div>
                <div class="ocms-fusion-alibaba-pc-element-shipping-country-discount b2b-ocms-fusion-comp"></div>
                <div class="sold">80,000+sold</div>
              </div>
            </a>
          </div>
      </div>
    </div>
</template>
<style lang="scss">
.pub{
  display: flex;
  height: 150px;
  background: #F3904F;  /* fallback for old browsers */
 background: -webkit-linear-gradient(to right, #f43a3a, #F3904F);  /* Chrome 10-25, Safari 5.1-6 */
 background: linear-gradient(to right, #f43a3a, #F3904F); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */

  .container{
    display: flex;
    align-items: center;
    .counter{
      padding: 0px 15px;
      display: flex;
      align-items: center;
      color: #fff;
      .title{
        font-weight: bold;
        font-size: 45px;
      }
      button{
        padding: 7px 7px;
        outline: none;
        border: 1px solid rgba($color: #fff, $alpha: 1.0);
        background: transparent;
        margin: 5px;
        font-weight: bold;
        color: #fff;
      }
      button.btn_day{
        padding: 8px;
        border: 0;
        background-color: rgba(255,255,255,.3);
      }
    }
    .nav{
      flex: 1;
      display: flex;
      justify-content: flex-end;
      padding: 0px 15px;
      a{
        margin: 0 10px;
        color: #fff;
        i{
          margin: 0 2px;
        }
      }
    }
  }
}
.zoom {
  transition: transform .2s; /* Animation */
}

.zoom:hover {
  transform: scale(1.1); /* (150% zoom - Note: if the zoom is too large, it will go outside of the viewport) */
}
.product-card{
      position: relative;
    overflow: hidden;
    display: inline-block;
    width: 230px;
    height: 320px;
    margin-right: 12px;
    margin-bottom: 12px;
    border-radius: 8px;
    box-shadow: 0 2px 8px 0 rgba(0,0,0,.05);
    background-color: #fff;
    .image-content{
        position: relative;
        overflow: hidden;
        display: -ms-flexbox;
        display: flex;
        -ms-flex-pack: center;
        justify-content: center;
        -ms-flex-align: center;
        align-items: center;
        width: 100%;
        height: 208px;
      .product-img{
        width: 168px;
        height: 168px;
        transition: transform 1.25s cubic-bezier(.165,.84,.44,1);
      }
      .product-img:hover{
        transform: scale(1.1); /* (150% zoom - Note: if the zoom is too large, it will go outside of the viewport) */
      }
    }
    .product-info{
      padding: 0 12px 12px 12px;
      color: #333;
      .price{
            font-weight: 700;
        font-size: 16px;
        overflow: hidden;
        white-space: nowrap;
        text-overflow: ellipsis;
        .price-cut-line {
        font-weight: 400;
          }
              .price-unit {
            font-size: 12px;
            color: #999;
            font-weight: 400;
        }
      }
      .origin-price-and-discount {
          margin-top: 4px;
          .origin-price {
          margin-right: 6px;
          font-size: 12px;
          color: #999;
          text-decoration: line-through;
         }
         .discount {
            height: 14px;
            padding: 1px 6px;
            border-radius: 4px;
            color: #fff;
            background-color: #f43a3a;
        }
      }
    }
}

</style>

<script>
export default {
  layout: 'alibaba',
  data () {
    return {
      day: 1,
      dayStr: "00",
      hour: 17,
      hourStr: "00",
      minute: 30,
      minuteStr: "00",
      second: 0,
      secondStr: "00",
      timer: null
    }
  },
  mounted () {
    if(this.day == 0 && this.hour == 0 && this.minute ==0 && this.second == 0) {
      this.stopTimer()
    }else {
      this.startTimer()
    }
  },
  computed: {
  
  },
  methods: {
    startTimer () {
     this.timer = setInterval(() => {
       

        if (this.second == 0) {
          if(this.minute > 0 ) {
           this.second = 59
           this.minute--
          }
        }
        if (this.minute == 0) {
         if(this.hour > 0){
           this.minute = 59
           this.hour--
         }
        }
        if (this.hour == 0) {
        
         if(this.day > 0) {
           this.hour = 24
           this.day--
         }
        }
       
      this.secondStr = this.toFormat(this.second)
      this.minuteStr = this.toFormat(this.minute)
      this.hourStr = this.toFormat(this.hour)
      this.dayStr = this.toFormat(this.day)
      if(this.second != 0){
      this.second--
      }

      }, 1000);
    },
    stopTimer () {
      if(this.timer != null) {
        clearInterval(this.timer)
      }
    },
    getImage(index) {
      return require(`@/assets/img/articles/${100+index}.webp`)
    },
    toFormat (t) {
      if(t < 10) {
        return "0"+t;
      }
      return t;
    }
  }
}
</script>
