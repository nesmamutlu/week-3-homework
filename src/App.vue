<template>
  <div id="app">
    <p>-Card içerisindeki title ve detail yazıları için birer slot oluşturup slotlar ile card componenti içerisine aktarınız</p>
    <Card />

    <br>
    <hr>
    <slot name="baslik1">
      <slot name="baslik2">
      <span>
        <h1 slot="baslik1"></h1>
        <span slot="baslik2"></span></span>

        <card>
    <br>

    <p>
      -Aşağıdaki div'i button ile gizle göster yapınız.<br>
      -Button text'i duruma göre show yada hide olacaktır.
      Hazırlanan 'buttonText' isimli computed'i bu şekilde update ediniz.<br>
      - İlgili div'i gizlerken ve gösterirken transition ile fade animasyonu ekleyiniz.
      (Animate.css ve hazır css'ler kullanmayınız)
    </p>
    <button>{{ buttonText }}</button>
    <br><br>
    <div class="box">
        Vue.js is awasome!!!
    </div>

    <br>
    <hr>
    <br>
    <button @click="seen =! seen"> {{ buttonText }}</button>
    <br /><br />
    <transition name="fade">
      <div class="box" v-show="seen">
        <p v-,f="seen">Vue.js is awasome!!! </p>
      </div>
    </transition>
     <br />
     <hr />
     <br />
     <transition appear>
     <div class="box">
         Vue.js is awasome!!!


     </div>
     </transition>


            <style>
                .fade-enter {
                    opacity: 0;
                }
                .fade-enter-active {
                    transition: opacity 1s;
                }
                .fade-leave {
                    opacity: 1;
                }
                .fade-leave-active {
                    transition: opacity 1s;
                    opacity: 0;



                }





                export default

                

                data() {

                    return {
                        seen: false,
          };
       },
          components: {
          Card,
          Price,
          Wrapper,
       },

          computed: {
           buttonText(){
             return this.seen ? 'hide' : 'show'
           },
       
        },

     };



    <p>

      - Aşağıdaki div'e sayfa loading <b><i>(appear)</i></b> olduktan sonra bir animate.css ile animasyon ekleyiniz.
      (Animete.css kullanmak zorunludur)
    </p>
     <br>
    <div class="box">
      I have a animation!!!!
    </div>

      <transition name="fade" appear>
      <div class="alert alert-info" v-if="isShow">

      </div>
      </transition>
      <hr>
      <br>
                .slide-enter {
                }
                .slide-enter-active {
                    animation: slide-in 1s ease-in;
                }
                .slide-leave {
                }
                .slide-leave-active {
                    animation: slide-out 1s ease-out;
                    transition: opacity 1s;
                    opacity: 0;
                    position: absolute;
                };

    <p>
      - Aşağıdaki component içerisindeki input'a girilen price'i formatTL filter'i ile filtre uygulayınız.<br>
      Örnek olarak çıktı 15 için '15.00 TL' olacaktır.

    </p>
    <Price />


    <br>
    <hr>
    <br>
    <input type="text" v-model="Price"
           placeholder="please enter price" />
     <br>

    Your total amount: {{ Price | Price | PriceSymbolTR }}
      <br> 
      <p>  
             Vue.filter(
                 'amount', (value) => {
                     return `${value}.00`;
                 }
                })



      - Mixins & EventBus example başlığını props ile wrapper componentine yazınız.<br>
      - 2 child component'i eventbus ile haberleştiriniz. Gelen mesajları "incoming message" kısmına yazınız <br>
      - 2 child component aynı işi yaptıkları için ortak kodları mixin içerisinde tutunuz.
      Not: sadece ortak olan kodlar mixin içerisinde olacak bu ayrıntıya dikkat edelim.
    </p>
    <Wrapper />

  </div>
</template>

<script>
import Card from './components/Card.vue'
import Price from './components/Price.vue'
import Wrapper from './components/Wrapper.vue'

export default {
  name: 'App',
  data() {
    return {
    }
  },
  components: {
    Card,
    Price,
    Wrapper,
  },
  computed: {
    buttonText() {
      return 'Show / Hide';
    }
  }
}
</script>

<style>
 #app {
   width: 800px;
   margin: auto;
 }
  .box {
    background-color: beige;
    border: solid 1px #ccc;
    padding: 10px;
  }
</style>
