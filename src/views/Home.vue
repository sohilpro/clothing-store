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
        img: '',
        price: '$71',
        title: 'Style three Parasut'
      },
      {
        img: '',
        price: '$71',
        title: 'Style three Parasut'
      },
      {
        img: '',
        price: '$71',
        title: 'Style three Parasut'
      },
      {
        img: '',
        price: '$71',
        title: 'Style three Parasut'
      },
      {
        img: '',
        price: '$71',
        title: 'Style three Parasut'
      },
      {
        img: '',
        price: '$71',
        title: 'Style three Parasut'
      },
      {
        img: '',
        price: '$71',
        title: 'Style three Parasut'
      },
      {
        img: '',
        price: '$71',
        title: 'Style three Parasut'
      },
    ],
    parkas:[
    {
        img: 'https://api.sailracing.com/storage/images/product/2131117/2131117_101_a.png',
        price: '$71',
        title: 'Style three Parasut'
    },
    {
        img: 'https://api.sailracing.com/storage/images/product/2031121/2031121_958_a.png',
        price: '$71',
        title: 'Style three Parasut'
    },
    {
        img: 'https://stellar.centracdn.net/client/dynamic/images/96_1d1bfd4f42-122green-001-m-guide-expedition-parka.png',
        price: '$71',
        title: 'Style three Parasut'
    },
    {
        img: 'https://stellar.centracdn.net/client/dynamic/images/96_c8f3534cb6-122orange-001-m-guide-expedition-parka.png',
        price: '$71',
        title: 'Style three Parasut'
    },
    {
        img: 'https://stellar.centracdn.net/client/dynamic/images/96_e2829ef08d-122dkgrey-001-m-guide-expedition-parka-medi.png',
        price: '$71',
        title: 'Style three Parasut'
    },
    {
        img: 'https://stellar.centracdn.net/client/dynamic/images/96_6f269e2780-122yellow-001-m-guide-expedition-parka.png',
        price: '$71',
        title: 'Style three Parasut'
    },
    {
        img: 'https://cdn11.bigcommerce.com/s-hgn1l9sh63/images/stencil/1000w/attribute_rule_images/3941_source_1665899449.png',
        price: '$71',
        title: 'Style three Parasut'
    },
    {
        img: 'https://buyma-global-prod-img.s3.amazonaws.com/img/upload/product_image/2e541017-54cd-4d50-b14d-9ecd7271a665/e17a40c6-0aaa-4ffe-9294-82279534d89d.PNG',
        price: '$71',
        title: 'Style three Parasut'
    },
    ],
    steves:[],
    dennis:[],
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