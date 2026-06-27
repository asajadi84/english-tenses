<template>
  <v-app>
    <v-locale-provider rtl>
      <v-main class="main-container">
        <v-app-bar color="#9C27B0">
          <v-app-bar-title>آموزش تعاملی زمان افعال انگلیسی</v-app-bar-title>
        </v-app-bar>

        <v-container>
          <v-card class="mb-8">
            <v-toolbar>
              <v-toolbar-title text="زمان و نوع فعل را انتخاب کنید:"></v-toolbar-title>
            </v-toolbar>
            <v-row class="mt-6 px-4">
              <v-col>
                <v-radio-group v-model="verbTime">
                  <v-radio label="گذشته" color="#9C27B0" :value="1"></v-radio>
                  <v-radio label="حال" color="#9C27B0" :value="2"></v-radio>
                  <v-radio label="آینده" color="#9C27B0" :value="3"></v-radio>
                </v-radio-group>
              </v-col>
              <v-col>
                <v-radio-group v-model="verbForm">
                  <v-radio label="ساده" color="#9C27B0" :value="1"></v-radio>
                  <v-radio label="استمراری" color="#9C27B0" :value="2"></v-radio>
                  <v-radio label="کامل" color="#9C27B0" :value="3"></v-radio>
                  <v-radio label="کامل استمراری" color="#9C27B0" :value="4"></v-radio>
                </v-radio-group>
              </v-col>
            </v-row>
          </v-card>

          <v-row>
            <v-col cols="12" md="6">
              <div>
                <v-scroll-x-transition mode="out-in">
                  <div class="title-text" v-if="verbTense == '01'"><span class="primary-text">Simple</span> <span>Past</span></div>
                  <div class="title-text" v-if="verbTense == '02'"><span class="primary-text">Simple</span> <span>Present</span></div>
                  <div class="title-text" v-if="verbTense == '03'"><span class="primary-text">Simple</span> <span>Future</span></div>
                  <div class="title-text" v-if="verbTense == '04'"><span>Past</span> <span class="primary-text">Continuous</span></div>
                  <div class="title-text" v-if="verbTense == '05'"><span>Present</span> <span class="primary-text">Continuous</span></div>
                  <div class="title-text" v-if="verbTense == '06'"><span>Future</span> <span class="primary-text">Continuous</span></div>
                  <div class="title-text" v-if="verbTense == '07'"><span>Past</span> <span class="primary-text">Perfect</span></div>
                  <div class="title-text" v-if="verbTense == '08'"><span>Present</span> <span class="primary-text">Perfect</span></div>
                  <div class="title-text" v-if="verbTense == '09'"><span>Future</span> <span class="primary-text">Perfect</span></div>
                  <div class="title-text" v-if="verbTense == '10'"><span>Past</span> <span class="primary-text">Perfect Continuous</span></div>
                  <div class="title-text" v-if="verbTense == '11'"><span>Present</span> <span class="primary-text">Perfect Continuous</span></div>
                  <div class="title-text" v-if="verbTense == '12'"><span>Future</span> <span class="primary-text">Perfect Continuous</span></div>
                </v-scroll-x-transition>

                <v-scroll-x-transition mode="out-in">
                  <div class="subtitle-text" v-if="verbTense == '01'"><span>گذشته</span> <span class="primary-text">ساده</span></div>
                  <div class="subtitle-text" v-if="verbTense == '02'"><span>حال</span> <span class="primary-text">ساده</span></div>
                  <div class="subtitle-text" v-if="verbTense == '03'"><span>آینده</span> <span class="primary-text">ساده</span></div>
                  <div class="subtitle-text" v-if="verbTense == '04'"><span>گذشته</span> <span class="primary-text">استمراری</span></div>
                  <div class="subtitle-text" v-if="verbTense == '05'"><span>حال</span> <span class="primary-text">استمراری</span></div>
                  <div class="subtitle-text" v-if="verbTense == '06'"><span>آینده</span> <span class="primary-text">استمراری</span></div>
                  <div class="subtitle-text" v-if="verbTense == '07'"><span>گذشته</span> <span class="primary-text">کامل</span></div>
                  <div class="subtitle-text" v-if="verbTense == '08'"><span>حال</span> <span class="primary-text">کامل</span></div>
                  <div class="subtitle-text" v-if="verbTense == '09'"><span>آینده</span> <span class="primary-text">کامل</span></div>
                  <div class="subtitle-text" v-if="verbTense == '10'"><span>گذشته</span> <span class="primary-text">کامل استمراری</span></div>
                  <div class="subtitle-text" v-if="verbTense == '11'"><span>حال</span> <span class="primary-text">کامل استمراری</span></div>
                  <div class="subtitle-text" v-if="verbTense == '12'"><span>آینده</span> <span class="primary-text">کامل استمراری</span></div>
                </v-scroll-x-transition>
              </div>

              <div class="image-container">
                <v-fade-transition>
                  <img class="pt-8" alt="Tense Animation" :src="`/tense-animations/${verbTense}.webp`" :key="verbTense">
                </v-fade-transition>
              </div>
            </v-col>
            <v-col cols="12" md="6">
              <div>
                <v-alert icon="mdi-book-information-variant" color="#9C27B0" variant="tonal">
                  <span v-if="verbTense == '01'">برای بیان اتفاقی که در گذشته رخ داده و به پایان رسیده است.</span>
                  <span v-if="verbTense == '02'">برای بیان اتفاقاتی که به طور معمول و یا از روی عادت رخ می‌دهند.</span>
                  <span v-if="verbTense == '03'">برای بیان اتفاقی که در آینده رخ خواهد داد.</span>
                  <span v-if="verbTense == '04'">برای بیان اتفاقی که رخ دادن آن از گذشته شروع شده، برای مدتی ادامه داشته و در همان گذشته به پایان رسیده است.</span>
                  <span v-if="verbTense == '05'">برای بیان اتفاقی که رخ دادن آن از گذشته شروع شده، هم اکنون در حال رخ دادن است و احتمالاً تا مدتی نیز ادامه داشته باشد.</span>
                  <span v-if="verbTense == '06'">برای بیان اتفاقی که در آینده رخ خواهد داد و پس از مدتی به پایان خواهد رسید.</span>
                  <span v-if="verbTense == '07'">برای بیان رخ دادن اتفاقی پیش از یک اتفاق دیگر (یا یک زمان مشخص) وقتی هر دو در گذشته رخ داده باشند.</span>
                  <span v-if="verbTense == '08'">برای بیان رخ دادن اتفاقی پیش از یک اتفاق دیگر (یا یک زمان مشخص) وقتی اتفاق دوم در زمان حال رخ داده باشد.</span>
                  <span v-if="verbTense == '09'">برای بیان رخ دادن اتفاقی پیش از یک اتفاق دیگر (یا یک زمان مشخص) وقتی هر دو در آینده رخ دهند.</span>
                  <span v-if="verbTense == '10'">برای بیان رخ دادن اتفاقی مستمر پیش از یک اتفاق دیگر (یا یک زمان مشخص) وقتی هر دو در گذشته رخ داده باشند.</span>
                  <span v-if="verbTense == '11'">برای بیان رخ دادن اتفاقی مستمر پیش از یک اتفاق دیگر (یا یک زمان مشخص) وقتی اتفاق دوم در زمان حال رخ داده باشد.</span>
                  <span v-if="verbTense == '12'">برای بیان رخ دادن اتفاقی مستمر پیش از یک اتفاق دیگر (یا یک زمان مشخص) وقتی هر دو در آینده رخ دهند.</span>
                </v-alert>
              </div>

              <v-card class="mt-4 p-2">
                <div class="centered-text" v-if="verbTense == '01'">
                  <p class="ltr-text">
                    Nima <span class="primary-text underlined-text">ate</span> pizza <span class="primary-text">last night</span>.
                    <v-icon-btn color="#9C27B0" icon="mdi-volume-high" size="small" variant="tonal" @click="TTS('Nima ate pizza last night.')" v-ripple></v-icon-btn>
                  </p>
                  <p>نیما <span class="primary-text">دیشب</span> پیتزا <span class="primary-text underlined-text">خورد</span>.</p>
                </div>
                <div class="centered-text" v-if="verbTense == '02'">
                  <p class="ltr-text">
                    Nima <span class="primary-text underlined-text">eats</span> pizza <span class="primary-text">every day</span>.
                    <v-icon-btn color="#9C27B0" icon="mdi-volume-high" size="small" variant="tonal" @click="TTS('Nima eats pizza every day.')" v-ripple></v-icon-btn>
                  </p>
                  <p>نیما <span class="primary-text">هر روز</span> پیتزا <span class="primary-text underlined-text">می‌خورد</span>.</p>
                </div>
                <div class="centered-text" v-if="verbTense == '03'">
                  <p class="ltr-text">
                    Nima <span class="primary-text underlined-text">will eat</span> pizza <span class="primary-text">tomorrow</span>.
                    <v-icon-btn color="#9C27B0" icon="mdi-volume-high" size="small" variant="tonal" @click="TTS('Nima will eat pizza tomorrow.')" v-ripple></v-icon-btn>
                  </p>
                  <p>نیما <span class="primary-text">فردا</span> پیتزا <span class="primary-text underlined-text">خواهد خورد</span>.</p>
                </div>
                <div class="centered-text" v-if="verbTense == '04'">
                  <p class="ltr-text">
                    Sina <span class="primary-text underlined-text">was drawing</span> <span class="primary-text">last night</span>.
                    <v-icon-btn color="#9C27B0" icon="mdi-volume-high" size="small" variant="tonal" @click="TTS('Sina was drawing last night.')" v-ripple></v-icon-btn>
                  </p>
                  <p>سینا <span class="primary-text">دیشب</span> <span class="primary-text underlined-text">نقاشی می‌کشید</span>.</p>
                </div>
                <div class="centered-text" v-if="verbTense == '05'">
                  <p class="ltr-text">
                    Sina <span class="primary-text underlined-text">is drawing</span> <span class="primary-text">right now</span>.
                    <v-icon-btn color="#9C27B0" icon="mdi-volume-high" size="small" variant="tonal" @click="TTS('Sina is drawing right now.')" v-ripple></v-icon-btn>
                  </p>
                  <p>سینا <span class="primary-text">الان (دارد)</span> <span class="primary-text underlined-text">نقاشی می‌کشد</span>.</p>
                </div>
                <div class="centered-text" v-if="verbTense == '06'">
                  <p class="ltr-text">
                    Sina <span class="primary-text underlined-text">will be drawing</span> <span class="primary-text">at this time tomorrow</span>.
                    <v-icon-btn color="#9C27B0" icon="mdi-volume-high" size="small" variant="tonal" @click="TTS('Sina will be drawing at this time tomorrow.')" v-ripple></v-icon-btn>
                  </p>
                  <p>سینا <span class="primary-text">فردا همین موقع</span> <span class="primary-text underlined-text">در حال نقاشی کشیدن خواهد بود</span>.</p>
                </div>
                <div class="centered-text" v-if="verbTense == '07'">
                  <p class="ltr-text">
                    I <span class="primary-text underlined-text">had done</span> my homework <span class="primary-text">before</span> my parents arrived.
                    <v-icon-btn color="#9C27B0" icon="mdi-volume-high" size="small" variant="tonal" @click="TTS('I had done my homework before my parents arrived.')" v-ripple></v-icon-btn>
                  </p>
                  <p>من تکالیفم را <span class="primary-text">قبل</span> از این که والدینم برسند <span class="primary-text underlined-text">انجام داده بودم</span>.</p>
                </div>
                <div class="centered-text" v-if="verbTense == '08'">
                  <p class="ltr-text">
                    I <span class="primary-text underlined-text">have done</span> my homework <span class="primary-text">already</span>.
                    <v-icon-btn color="#9C27B0" icon="mdi-volume-high" size="small" variant="tonal" @click="TTS('I have done my homework already.')" v-ripple></v-icon-btn>
                  </p>
                  <p>من تکالیفم را <span class="primary-text">از قبل</span> <span class="primary-text underlined-text">انجام داده‌ام</span>.</p>
                </div>
                <div class="centered-text" v-if="verbTense == '09'">
                  <p class="ltr-text">
                    I <span class="primary-text underlined-text">will have done</span> my homework <span class="primary-text">before</span> my parents arrive.
                    <v-icon-btn color="#9C27B0" icon="mdi-volume-high" size="small" variant="tonal" @click="TTS('I will have done my homework before my parents arrive.')" v-ripple></v-icon-btn>
                  </p>
                  <p>من تکالیفم را <span class="primary-text">قبل</span> از این که والدینم برسند <span class="primary-text underlined-text">انجام خواهم داد</span>.</p>
                </div>
                <div class="centered-text" v-if="verbTense == '10'">
                  <p class="ltr-text">
                    Sara <span class="primary-text underlined-text">had been driving</span> for one hour <span class="primary-text">before</span> she left the city.
                    <v-icon-btn color="#9C27B0" icon="mdi-volume-high" size="small" variant="tonal" @click="TTS('Sara had been driving for one hour before she left the city.')" v-ripple></v-icon-btn>
                  </p>
                  <p>سارا <span class="primary-text">قبل</span> از این که شهر را ترک کند برای یک ساعت <span class="primary-text underlined-text">رانندگی کرده بود</span>.</p>
                </div>
                <div class="centered-text" v-if="verbTense == '11'">
                  <p class="ltr-text">
                    Sara <span class="primary-text underlined-text">has been driving</span> for one hour <span class="primary-text">now</span>.
                    <v-icon-btn color="#9C27B0" icon="mdi-volume-high" size="small" variant="tonal" @click="TTS('Sara has been driving for one hour now.')" v-ripple></v-icon-btn>
                  </p>
                  <p>سارا <span class="primary-text">تا الان</span> برای یک ساعت <span class="primary-text underlined-text">رانندگی کرده است</span>.</p>
                </div>
                <div class="centered-text" v-if="verbTense == '12'">
                  <p class="ltr-text">
                    Sara <span class="primary-text underlined-text">will have been driving</span> for one hour <span class="primary-text">before</span> she leaves the city.
                    <v-icon-btn color="#9C27B0" icon="mdi-volume-high" size="small" variant="tonal" @click="TTS('Sara will have been driving for one hour before she leaves the city.')" v-ripple></v-icon-btn>
                  </p>
                  <p>سارا <span class="primary-text">قبل</span> از این که شهر را ترک کند برای یک ساعت <span class="primary-text underlined-text">رانندگی خواهد کرد</span>.</p>
                </div>
              </v-card>
            </v-col>
          </v-row>
          <p class="ltr-text secondary-text mt-4 mb-10">
            © 2026 Designed & Developed by <strong class="px-1"><a href="https://sajadidev.ir" target="_blank">SajadiDev</a></strong>
          </p>
        </v-container>
      </v-main>
    </v-locale-provider>

    <v-fab color="#9C27B0" icon="mdi-arrow-left" app location="left bottom" @click="incTense" :disabled="verbTense == '12'"><v-icon v-tooltip:top="'بعدی'"></v-icon></v-fab>
    <v-fab color="#9C27B0" icon="mdi-arrow-right" app location="right bottom" @click="decTense" :disabled="verbTense == '01'"><v-icon v-tooltip:top="'قبلی'"></v-icon></v-fab>

  </v-app>
</template>

<script setup>
  import { computed, ref } from 'vue'

  const verbTime = ref(1);
  //1 = past, 2 = present, 3 = future

  const verbForm = ref(1);
  //1 = simple, 2 = continuous, 3 = perfect, 4 = perfect continuous

  const verbTense = computed(() => {
    if(verbForm.value == 1){
      if(verbTime.value == 1){
        return '01';
      }else if(verbTime.value == 2){
        return '02';
      }else{
        return '03';
      }
    }else if(verbForm.value == 2){
      if(verbTime.value == 1){
        return '04';
      }else if(verbTime.value == 2){
        return '05';
      }else{
        return '06';
      }
    }else if(verbForm.value == 3){
      if(verbTime.value == 1){
        return '07';
      }else if(verbTime.value == 2){
        return '08';
      }else{
        return '09';
      }
    }else{
      if(verbTime.value == 1){
        return '10';
      }else if(verbTime.value == 2){
        return '11';
      }else{
        return '12';
      }
    }
  });

  function TTS(txt){
    let utterance = new SpeechSynthesisUtterance(txt);
    speechSynthesis.speak(utterance);
  }

  function incTense(){
    if(verbTime.value < 3){
      verbTime.value++;
    }else{
      verbTime.value = 1;
      if(verbForm.value < 4){
        verbForm.value++;
      }else{
        verbForm.value = 1;
      }
    }
  }

  function decTense(){
    if(verbTime.value > 1){
      verbTime.value--;
    }else{
      verbTime.value = 3;
      if(verbForm.value > 1){
        verbForm.value--;
      }else{
        verbForm.value = 4;
      }
    }
  }

</script>

<style>
  .main-container {
    background-color: #FAFAFA;
  }
  .title-text {
    font-weight: bold;
    font-size: 1.8rem;
  }
  .subtitle-text {
    font-size: 1.4rem;
  }
  .primary-text {
    color: #9C27B0;
  }
  .secondary-text {
    color: #9E9E9E;
  }
  .ltr-text {
    direction: ltr;
  }
  .underlined-text {
    text-decoration: underline;
  }
  .centered-text {
    text-align: center;
  }
  .image-container {
    position: relative;
    width: 100%;
    aspect-ratio: 3 / 1;
  }
  .image-container img {
    position: absolute;
  }
</style>