<template>
  <div class="">
    <div class="topbar">
        <div class="bloc-left">
            <img src="@/assets/img/logo.png" width="150"  alt="">
        </div>
        <div class="bloc-right">
          <div class="nav">
            <ul>
                <li><a href="">Ready to Ship</a></li>  
                <li>|</li>  
                <li><a href="">Trade Shows</a></li>  
                <li>|</li>
                <li><a href="">Get the App</a></li>
                <li>|</li>
            </ul>
          </div>
          <div class="lang">
            <a class="lang-nav" href="#">English</a>
            <div class="list-lang">
                <ul>
                    <li><a href="#">English</a></li>
                    <li><a href="#">Deutsch</a></li>
                    <li><a href="#">Portugues</a></li>
                    <li><a href="#">Espagnol</a></li>
                    <li><a href="#">Francais</a></li>
                    <li><a href="#">Italiano</a></li>
                    <li><a href="#">Pусский</a></li>
                </ul>

            </div>
        </div>
        </div>
       
    </div>
    <div class="header">
       <div class="brand">
           <img src="@/assets/img/logo.png" width="210" alt="">
       </div>
        <div class="search">
            <div class="box">
                <button class="btn-filter">Products<i class="fas fa-angle-down"></i></button>
                <input type="text" placeholder="What are you looking for">
                <button class="btn-search">Search</button>
            </div>
        </div>
        <div class="nav-right">
            <ul>
                <li>
                    <a href="">
                        <img src="@/assets/img/icons/user.svg" alt="">
                        <span>Sign in</span>
                    </a>
                </li>
                <li>
                    <a href="">
                        <img src="@/assets/img/icons/shopping-bag.svg" alt="">
                        <span>Orders</span>
                    </a>
                </li>
                <li>
                    <a href="">
                        <img src="@/assets/img/icons/like.svg" alt="">
                        <span>Favorites</span>
                    </a>
                </li>
                <li>
                    <a href="">
                        <img src="@/assets/img/icons/shopping-cart.svg" alt="">
                        <span>Cart</span>
                    </a>
                </li>
            </ul>
        </div>
    </div>
    <div class="navbar">
         <div class="menu">
             
                <a class="menu_link" href="#">
            <i class="fas fa-list-ul"></i>
            <span>Categories</span>
            <i class="fas fa-angle-down"></i>
            </a>
            <div class="list-menu">
                <ul>
                    <li><a href=""></a></li>
                </ul>
            </div>
        </div>
         <div class="nav">
           <ul>
               <li class="separator">|</li>
               <li><a class="nav_link" href="#">Ready to ship</a></li>
               <li><a class="nav_link" href="#">Trade shows</a></li>
               <li><a class="nav_link" href="#">Membership<i class="fas fa-angle-down"></i></a></li>
               <li><a class="nav_link" href="#">Services<i class="fas fa-angle-down"></i></a></li>
               <li><a class="nav_link" href="#">Helps<i class="fas fa-angle-down"></i></a></li>
           </ul>
        </div>
        <div class="nav-right">
            <ul>
                <li><a href="">Get the App</a></li>
                <li class="separator">|</li>
                <li><a href="">English-USD<i class="fas fa-angle-down"></i></a></li>
            </ul>
        </div>
    </div>
    <div class="main">
        <nuxt/>
    </div>
  </div>
</template>
<style lang="scss">
@import url('https://use.fontawesome.com/releases/v5.8.2/css/all.css');
*, *::before, *::after{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
a{
    text-decoration: none;
    color: inherit ;
}
.topbar{
    display: none;
    justify-content: space-between;
    ul{
        list-style: none;
    }
    .bloc-left{
        padding: 0 20px;
        display: flex;
        align-items: center;
    }
    .bloc-right{
        display: flex;
       .nav{
          ul{
            display: flex;
            padding: 0px 10px;
            li{
            color: #777;
            padding: 10px 5px;
            display: flex;
            align-items: center;
           }
         }
       }
       .lang{
           position: relative;
           display: flex;
           align-items: center;
           padding-right: 10px;
          
           .list-lang{
               display: none;
               background: #fff;
               box-shadow: 0px 2px 6px rgba(0, 0, 0, 0.3);
               ul{
                   li{
                       padding: 10px 20px;
                   }
                   li:hover{
                       background: #f5f5f5;
                   }
               }
           }
           .list-lang::before {
                content:"";
                position: absolute;
                left: 60px;
                top: -10px;
                width: 0;
                height: 0;
                border-style: solid;
                border-width: 0 10px 10px 10px;
                border-color: transparent transparent #f5f5f5 transparent;
                z-index:9999;
            }
       }
        .lang:hover  .list-lang{
          display: block;
          position: absolute;
          top: 38px;
          right: 0;
          z-index: 99;
        }
    }
}
.header{
    display: flex;
    background: #fff;
    border: 1px solid #eee;
    .fa-angle-down{
        font-size: 12px;
        margin-left: 5px;
        margin-top: 2px;
        transition: transform 1s;
    }
    .brand{
        display: flex;
        padding: 15px;
    }
    .search{
        flex: 1;
        display: flex;
        align-items: center;
        .box{
            display: flex;
            width: 90%;
            margin: 0 auto;
            border: 2px solid tomato;
            border-radius: 20px;
            input{
                flex: 1;
                outline: none;
                border: 0;
                background: transparent;
                padding: 0 10px;
            }
            .btn-filter{
                outline: none;
                border:0;
                background: transparent;
                border-right: 1px solid #f5f5f5;
                padding: 5px 10px;
            }
            .btn-search{
               outline: none;
               border:0;
               background: tomato;
               color: #fff;
               padding: 10px 15px;
               border-radius: 0px 20px 20px 0px;
            }
        }
    }
    .nav-right{
        width: 300px;
        display: flex;
        align-items: center;
        ul{
          display: flex;
          list-style: none;
          li{
              a{
                  display: flex;
                  flex-direction: column;
                  justify-content: center;
                  align-items: center;
                  padding: 10px 15px;
                  img{
                      width: 24px;
                  }
                 
              }
              a:hover{
                color: tomato;
              }
          }
        }
    }
}
.navbar{
    position: -webkit-sticky;
    position: sticky;
    top: 0;
    display: flex;
    background: #fff;
    z-index: 90;
    box-shadow: 0 5px 4px -6px rgba(0, 0, 0, 0.3);
    .menu{
        position: relative;
        border: 1px solid transparent;
        display: flex;
        margin-left: 10px;
        align-items: center;
        .menu_link{
            padding: 0 15px;
            position: relative;
            color: #555;
            
        }
       
        .list-menu{
            z-index: -1;
            position: absolute;
            width: 300px;
            height: 350px;
            display: none;
            top: 46px;
            left: -1px;
            background: #fff;
            box-shadow: 0px 0px 0px rgba(0, 0, 0, 0.3);
            // -webkit-box-shadow: 0 8px 6px -6px rgba(0, 0, 0, 0.3);
            // -moz-box-shadow: 0 8px 6px -6px rgba(0, 0, 0, 0.3);
            // box-shadow: 0 8px 6px -6px rgba(0, 0, 0, 0.3);
            border-style: solid;
            border-width: 1px 1px 1px 1px;
            border-color: rgba(0, 0, 0, 0.3);
            ul{
                margin: 0;
                padding: 0;
                list-style: none;
            }
        }
    }
    .menu:hover{
        border-color: rgba(0, 0, 0, 0.3);
        border-bottom-color: #fff;
        .menu_link{
            color: tomato;
        }
        .list-menu{
            display: block;
        }
        .fa-angle-down{
                font-size: 12px;
            }
    }
    .nav{
        flex: 1;
        display: flex;
        align-items: center;
        padding: 0 10px;
       position: relative;
    
       ul{
           display: flex;
           list-style: none;
           li{
               padding: 15px 15px 15px 0px;
               color: #555;
              .nav_link{
                display: flex;
                align-items: center;
              
               }
               .nav_link:hover{
                .fa-angle-down{
                    transform: rotateX(180deg);
                }
               }
              
           }
           
       }
      
       
    }
    .nav-right{
        display: flex;
        ul{
         padding: 0 10px;
         list-style: none;
          display: flex;
          align-items: center;
          li{
              color: #555;
          }
          .separator{
              padding: 0 10px;
          }
        }
    }
    .fa-angle-down{
        font-size: 12px;
        margin-left: 5px;
        margin-top: 2px;
        transition: transform 1s;
    }
}
.container{
    width: 90%;
    margin: 0 auto;
}
.main{
    min-height: 100vh;
    background: #EEE;
}
@keyframes spin { 100% { transform: rotate(180deg); } }
</style>
