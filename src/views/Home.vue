<template>
  <v-app :style="{ background: $vuetify.theme.themes.dark.background }">
    <Sidebar />
    <Navbar/>
    <v-container fluid> 
      <v-app-bar dark color="transparent" flat>
        <v-tabs color="#f34f64" v-model="tab">
          <v-tabs-slider color="#f34f64"></v-tabs-slider>
            <v-tab class="withoutupercase">Parasut</v-tab>
            <v-tab class="withoutupercase">Parka</v-tab>
            <v-tab class="withoutupercase">Steve</v-tab>
            <v-tab class="withoutupercase">Dennis</v-tab>
        </v-tabs>
      </v-app-bar>
      <v-card tile color="#323850" class="my-2 card_global">
        <v-row>
          <v-col cols="12" sm="8">
            <v-tabs-items v-model="tab">
              <v-tab-item>
                <v-card flat class="card_item pa-2">
                  <v-row>
                    <v-col cols="12" sm="3" v-for="(product, index) in products" :key="index">
                    <v-hover v-slot="{hover}" close-delay="200">
                    <v-card :elevation="hover ? 16 : 2" :class="{'on-hover' : hover}" 
                    class="mx-auto" height="250" tile color="#333c51" align-center align="center">
                      <v-card-actions>
                        <v-spacer></v-spacer>
                        <v-btn tile small :color="hover ? '#f34f64' : '#777d8b'" dark>{{ product.price }}</v-btn>
                      </v-card-actions>
                      <v-img :src=product.img width="150" height="150"></v-img>
                      <v-card-text :class="hover ? 'red--text' : 'white--text'">
                        {{ product.title }}
                      </v-card-text>
                     </v-card>
                    </v-hover>
                    </v-col>
                  </v-row>
                </v-card>
              </v-tab-item>
              <v-tab-item>
                <v-card flat class="card_item pa-2">
                  <v-row>
                    <v-col cols="12" sm="3" v-for="(parka, index) in parkas" :key="index">
                    <v-hover v-slot="{hover}" close-delay="200">
                    <v-card :elevation="hover ? 16 : 2" :class="{'on-hover' : hover}" 
                    class="mx-auto" height="250" tile color="#333c51" align-center align="center"
                    >
                      <v-card-actions>
                        <v-spacer></v-spacer>
                        <v-btn tile small color="hover ? '#f34f64' : '#777d8b'" dark>{{ parka.price }}</v-btn>
                      </v-card-actions>
                      <v-img :src=parka.img width="150" height="150"></v-img>
                      <v-card-text :class="hover ? 'red--text' : 'white--text'">
                        {{ parka.title }}
                      </v-card-text>
                     </v-card>
                    </v-hover>
                    </v-col>
                  </v-row>
                </v-card>
              </v-tab-item>
              <v-tab-item>
                <v-card flat class="card_item pa-2">
                  <v-row>
                    <v-col cols="12" sm="3" v-for="(steve, index) in steves" :key="index">
                    <v-hover v-slot="{hover}" close-delay="200">
                    <v-card :elevation="hover ? 16 : 2" :class="{'on-hover' : hover}" 
                    class="mx-auto" height="250" tile color="#333c51" align-center align="center"
                    >
                      <v-card-actions>
                        <v-spacer></v-spacer>
                        <v-btn tile small color="hover ? '#f34f64' : '#777d8b'" dark>{{ steve.price }}</v-btn>
                      </v-card-actions>
                      <v-img :src=steve.img width="150" height="150"></v-img>
                      <v-card-text :class="hover ? 'red--text' : 'white--text'">
                        {{ steve.title }}
                      </v-card-text>
                     </v-card>
                    </v-hover>
                    </v-col>
                  </v-row>
                </v-card>
              </v-tab-item>
              <v-tab-item>
                <v-card flat class="card_item pa-2">
                  <v-row>
                    <v-col cols="12" sm="3" v-for="(denni, index) in dennis" :key="index">
                    <v-hover v-slot="{hover}" close-delay="200">
                    <v-card :elevation="hover ? 16 : 2" :class="{'on-hover' : hover}" 
                    class="mx-auto" height="250" tile color="#333c51" align-center align="center"
                    >
                      <v-card-actions>
                        <v-spacer></v-spacer>
                        <v-btn tile small color="hover ? '#f34f64' : '#777d8b'" dark>{{ denni.price }}</v-btn>
                      </v-card-actions>
                      <v-img :src=denni.img width="150" height="150"></v-img>
                      <v-card-text :class="hover ? 'red--text' : 'white--text'">
                        {{ denni.title }}
                      </v-card-text>
                     </v-card>
                    </v-hover>
                    </v-col>
                  </v-row>
                </v-card>
              </v-tab-item>
            </v-tabs-items>
          </v-col>
          <v-col cols="12" sm="4">
            <Payment/>
          </v-col>
        </v-row>
      </v-card>
    </v-container>
  </v-app>
</template>

<script>
import Sidebar from "@/components/SideBar.vue";
import Navbar from "@/components/Navbar.vue";
import Payment from "@/components/Payment.vue";
export default{
  name: 'Home',
  data: () =>({
    tab: null,
    products: [
      {
        img: 'https://bbshop.ir/image/cache/catalog/b66041503%20(2)-550x450h.png',
        price: '$21',
        title: 'Style three Parasut'
      },
      {
        img: 'https://pelaziocdn.com/JwfBlIbEjVwKnSEVBIms7t1jVwY=/800x800/filters:quality(80):format(webp)/http://static.pelazio.com/upload/photo/202012/02/15/738b4a33a99b249afc86b100e6891d55.png',
        price: '$5',
        title: 'Style five Parasut'
      },
      {
        img: 'https://www.lilianmode.ir/wp-content/uploads/2022/03/IMG_4697-copy.png',
        price: '$93.33',
        title: 'Style eight Parasut'
      },
      {
        img: 'https://pelaziocdn.com/yNYxp592fryvtMTgPwaVW-mr-Po=/400x400/filters:quality(80):format(webp)/http://static.pelazio.com/upload/photo/202008/18/13/ef53d4aa220af666a79aa6d999244055.png',
        price: '$100',
        title: 'Style nine Parasut'
      },
      {
        img: 'https://bbshop.ir/image/cache/catalog/b67871105-550x450h.png',
        price: '$66.6',
        title: 'Style seven Parasut'
      },
      {
        img: 'https://fstools.ir/wp-content/uploads/2013/06/%D9%BE%D8%A7%D8%B1%D8%B3%D8%A7.png',
        price: '$70.23',
        title: 'Style four Parasut'
      },
      {
        img: 'https://zanbil.avin-tarh.ir/demo/fashion/wp-content/uploads/2018/10/cushion10-300x300.png',
        price: '$20',
        title: 'Style one Parasut'
      },
      {
        img: 'https://cdnfa.com/delband/f1e6/files/thumb/4742067.png',
        price: '$23',
        title: 'Style two Parasut'
      },
    ],
    parkas:[
    {
        img: 'https://api.sailracing.com/storage/images/product/2131117/2131117_101_a.png',
        price: '$71',
        title: 'Style six Parasut'
    },
    {
        img: 'https://api.sailracing.com/storage/images/product/2031121/2031121_958_a.png',
        price: '$71',
        title: 'Style two Parasut'
    },
    {
        img: 'https://stellar.centracdn.net/client/dynamic/images/96_1d1bfd4f42-122green-001-m-guide-expedition-parka.png',
        price: '$71',
        title: 'Style three Parasut'
    },
    {
        img: 'https://stellar.centracdn.net/client/dynamic/images/96_c8f3534cb6-122orange-001-m-guide-expedition-parka.png',
        price: '$71',
        title: 'Style four Parasut'
    },
    {
        img: 'https://stellar.centracdn.net/client/dynamic/images/96_e2829ef08d-122dkgrey-001-m-guide-expedition-parka-medi.png',
        price: '$71',
        title: 'Style three Parasut'
    },
    {
        img: 'https://stellar.centracdn.net/client/dynamic/images/96_6f269e2780-122yellow-001-m-guide-expedition-parka.png',
        price: '$71',
        title: 'Style seven Parasut'
    },
    {
        img: 'https://stellar.centracdn.net/client/dynamic/images/112_1827140252-152dkgrey-02-m-stretch-down-jacket_new-medi.png',
        price: '$71',
        title: 'Style nine Parasut'
    },
    {
        img: 'https://buyma-global-prod-img.s3.amazonaws.com/img/upload/product_image/2e541017-54cd-4d50-b14d-9ecd7271a665/e17a40c6-0aaa-4ffe-9294-82279534d89d.PNG',
        price: '$71',
        title: 'Style five Parasut'
    },
  ],
    steves:[
    {
        img: 'https://images.emojiterra.com/google/noto-emoji/v2.034/512px/1fa82.png',
        price: '$87',
        title: 'Style eight Parasut'
    },    
    {
        img: 'https://cdn11.bigcommerce.com/s-7tqzhr7u3z/images/stencil/1280x1280/products/6823/5361/185037__89335.1662664214.png?c=2',
        price: '$71.8',
        title: 'Style six Parasut'
    },    
    {
        img: 'https://community.cloudflare.steamstatic.com/economy/image/-8zOYQcPJoBYU7uKzjw0RZajjFiA_AojfFoacglhStOfdn6gbpcbDuuPIxAI88oXKSa_pIsdQy9UTOmvsw_2W9ArPI-0F4HfTGrmNvvn0ptfIA/360fx360f',
        price: '$99.99',
        title: 'Style ten Parasut'
    },   
    {
        img: 'https://images.twinkl.co.uk/tr/image/upload/t_illustration/illustation/parachute.png',
        price: '$52',
        title: 'Style eleven Parasut'
    },   
    {
        img: 'https://images.emojiterra.com/twitter/v13.1/512px/1fa82.png',
        price: '$692',
        title: 'Style one Parasut'
    },    
    {
        img: 'https://assets.stickpng.com/images/5a5a616514d8c4188e0b0852.png',
        price: '$48.2',
        title: 'Style three Parasut'
    },    
    {
        img: 'https://files.oyebesmartest.com/uploads/large/11565356184xzbwziygd8arua2popo9emz1wa4r3ob82ngwogwe9osdo1ayqr7tlkttwvwyddilnkwn2opnurnsh03ticqjbdrkdhk1d98yeo7n.png',
        price: '$78.9',
        title: 'Style six Parasut'
    },    
    {
        img: 'https://s3.amazonaws.com/s3.timetoast.com/public/uploads/photo/4148397/image/aa7e3b0e29430bb25d0c897cec2371b7',
        price: '$71',
        title: 'Style seven Parasut'
    },
    ],
    dennis:[
    {
      img: 'https://pelaziocdn.com/YHr3OXWaeLWAkuaXRF7L5h943R4=/1200x1200/filters:quality(80):format(webp)/http://static.pelazio.com/upload/photo/202009/02/12/bd54a1f3838dfb9304a0f46440eaf417.png',
      price: '$53.99',
      title: 'Style eight Parasut'
    },
    {
      img: 'https://pelaziocdn.com/cgDQdatduWu_20lsQpTcLpcDDa8=/400x400/filters:quality(80):format(webp)/http://static.pelazio.com/upload/photo/202008/25/14/34c9e280335c6d4f94275d1625e7badb.png',
      price: '$50.9',
      title: 'Style nine Parasut'
    },
    {
      img: 'https://www.ruderecords.com/wp-content/uploads/sites/104/2022/03/Superlove_Y2K_Tee.png',
      price: '$99.99',
      title: 'Style two Parasut'
    },
    {
      img: 'https://chapchi.com/system/extra_pages/all-over-tshirt-men.png',
      price: '$77',
      title: 'Style eight Parasut'
    },
    {
      img: 'https://papazh.com/storage/gallery/02029/wp.png',
      price: '$88.29',
      title: 'Style one Parasut'
    },
    {
      img: 'https://tarhbato.com/wp-content/uploads/2022/02/4.png',
      price: '$71.49',
      title: 'Style seven Parasut'
    },
    {
      img: 'https://chehape.ir/resources/images/cottontshirt.png',
      price: '$95.59',
      title: 'Style five Parasut'
    },
    {
      img: 'https://tantak.ir/assets/db_imgs/new_added/IMG-2022-02-07--14-26-54-index.png',
      price: '$88',
      title: 'Style two Parasut'
    },
    ],
  }),
  components:{
    Sidebar,
    Navbar,
    Payment,
  }
}
</script>

<style scoped>
.v-tabs-slider{
  position: absolute;
  top: 30%;
  left: 50%;
  transform: translate(-50%,-50%);
  height: 15px !important;
  width: 20px !important;
  border-radius: 150px 150px 0 0;
  background-color: #f34f64;
}
.v-tab.withoutupercase{
  text-transform: none !important;
}
.v-tabs{
  width: 50% !important;
}
.container{
  padding: 0 !important;
}
.v-card.card_global{
  height: 800px !important;
}
.theme--light.v-card.card_item{
  background-color: #323850 !important;
  color: #babecb !important;
}
.v-sheet.v-card.card_item{
  border-radius: 0px !important;
}
.v-btn:not(.v-btn--round).v-size--small{
  width: 50px !important;
}
.v-application .red--text{
  color: #f34f64 !important;
  caret-color: #f34f64 !important;
}
</style>