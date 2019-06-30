<template>
  <div class="container">
    <div class="search">
        <input v-model="searchItem" type="search" placeholder="What are you looking for">
        <button class="btn-search"><i class="fas fa-search"></i></button>
    </div>
    <div class="grid">
      <a :href="item.url" class="item" v-for="(item, j) in filteredItems" :key="j" target="_blank">
        <div class="logo">
          <img :src="loadImage(item.logo)" alt="">
        </div>
        <div class="title">{{item.title}}</div>
      </a>
    </div>
  </div>
</template>
<script>
export default {
  data () {
    return {
      items : [
        { id: 1, title: 'Alibaba', logo: 'logo.png', url: '/clones/alibaba'},
        { id: 2, title: 'CGL Group', logo: 'cgl.png', url: 'http://cglgroup.ci'},
        { id: 3, title: '07Store', logo: '07shop.png', url: 'http://07store.cglgroup.ci/catalog/smartphones'},
        { id: 4, title: 'Action medicale', logo: 'actionmedi.png', url: 'https://solution-actionmedicale.com/'},
        // { id: 5, title: 'Ecobank', logo: 'ecobank.svg', url: 'https://ecobank.com/ci/personal-banking'},
        { id: 6, title: 'BNI', logo: 'bni.jpg', url: 'https://www.bni.ci'},
        { id: 6, title: 'SweetComm', logo: 'Sweetcomm.png', url: 'http://www.sweet-comm.com/'},
      ],
      searchItem: ''
    }
  },
  computed: {
    filteredItems () {
      return this.items.filter((item) => {
        return item.title.toLowerCase().match(this.searchItem.toLowerCase())
      })
    }
  },
  methods: {
    loadImage (src) {
      return require(`@/assets/img/${src}`)
    },

  }
}
</script>


<style lang="scss" scoped>

.container{
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  width: 80%;
  min-height: 100vh;
 
}
.search{
  width: 60%;
  background: #fafafa;
  display: flex;
  align-items: center;
  border-radius: 5px;
  box-shadow: 0px 2px 4px rgba($color: #000000, $alpha: 0.3);
  input,button{
    outline: none;
    border: 0;
    background: transparent;
  }
  input{
    flex: 1;
    padding: 20px 10px;
    font-size: 16px;
  }
  button{
    padding: 10px 15px;
    font-size: 20px;
    color: #999;
  }
}
.grid{
  margin: 30px 0;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 20px;

  .item{
    display: flex;
    align-items: center;
    flex-direction: column;
    .logo{
      background: rgba($color: #000000, $alpha: 0.3);
      width: 150px;
      height: 100px;
      border-radius: 20px;
      display: flex;
      align-items: center;
      justify-content: center;
      transition: background .5s;
      img{
        max-width: 100px;
        height: auto;
      }
    }
    .title{
      color: #fafafa;
      font-size: 18px;
      font-weight: bold;
      margin: 5px;
    }
  }
  .item:hover .logo{
    background: rgba($color: #000000, $alpha: 0.5);
  }
}
</style>
