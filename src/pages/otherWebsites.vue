<template>
  <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mx-[5vw]">
    <div class="card bg-base-100 shadow-xl">
      <div class="card-body">
        <h2 class="card-title text-aaa">語聽相關公會</h2>
        <div class="overflow-x-auto">
          <table class="table">
            <!-- head -->
            <thead>
              <tr>
                <th>公會名稱</th>
              </tr>
            </thead>
            <tbody>
              <!-- row 1 -->
              <tr
                v-for="(item, index) in data"
                :class="`hover:bg-sky-100  ${
                  index % 2 == 0 ? 'bg-white' : 'bg-slate-100'
                }`"
              >
                <td>
                  <div class="tooltip tooltip-primary" data-tip="前往網站">
                    <a :href="item.url"> {{ item.title }}</a>
                  </div>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>

    <div class="card bg-base-100 shadow-xl">
      <div class="card-body">
        <h2 class="card-title text-aaa">聽語學術單位</h2>
        <div class="overflow-x-auto">
          <table class="table table-zebra">
            <!-- head -->
            <thead>
              <tr>
                <th>單位名稱</th>
              </tr>
            </thead>
            <tbody>
              <!-- row 1 -->
              <tr v-for="(item, index) in data1">
                <td>
                  <div class="tooltip tooltip-primary" data-tip="前往網站">
                    <a href=""> {{ item }}</a>
                  </div>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

// const GetPageInfo = async (url) => {
//   const response = await fetch(url)
//   const html = await response.text()
//   const title = document.querySelector('title', html).textContent
//   const favicon = document.querySelector('link[rel="icon"]', html).href
//   return { title, favicon }
// }
let index = 1
const GetPageInfo = (url) => {
  const iframe = document.createElement('iframe')
  iframe.id = index
  index++
  iframe.src = url
  iframe.onload = () => {
    console.log(iframe)

    const title = iframe.contentDocument?.title
    // const favicon = iframe.contentDocument.querySelector(
    //   'link[rel="shortcut icon"]'
    // ).href

    if (title) {
      data.value.push({ title })
      console.log(data.value)
    }
  }

  document.body.appendChild(iframe)
}

const urls = [
  'http://taiwanslpu.org.tw/',
  'http://taipeislpu.blogspot.com/',
  'http://ntpslp.blogspot.tw/',
  'http://tcslpunion.blogspot.com/',
  'https://sites.google.com/site/hscslp2013/',
  'http://miaolislp.blogspot.tw/',
  'http://taichungslp.blogspot.com/',
  'http://changhuaslp.blogspot.com/',
  'http://yunlinslp.blogspot.tw/',
  'http://www.chiayi.audio/',
  'http://tainanslp.blogspot.com/',
  'http://yilanslp.blogspot.tw/',
  'http://taichungaud.blogspot.com/',
  'http://tainanaud.blogspot.com/',
  'http://audiometryks.blogspot.com/'
]

// const data = ref([])

// urls.forEach((x) => {
//   GetPageInfo(x)
// })

const data = [
  {
    url: 'http://taiwanslpu.org.tw/',
    title: '中華民國語言治療師公會全國聯合會'
    // icon: 'http://taiwanslpu.org.tw/catalog/view/theme/default/stylesheet/assets/images/favicon.png'
  },
  {
    url: 'http://taipeislpu.blogspot.com/',
    title: '台北市語言治療師公會'
    // icon: 'http://taiwanslpu.org.tw/catalog/view/theme/default/stylesheet/assets/images/favicon.png'
  },
  {
    url: 'http://ntpslp.blogspot.tw/',
    title: '新北市語言治療師公會'
    // icon: 'http://taiwanslpu.org.tw/catalog/view/theme/default/stylesheet/assets/images/favicon.png'
  },
  {
    url: 'http://taipeislpu.blogspot.com/',
    title: '桃園市語言治療師公會'
    // icon: 'http://taiwanslpu.org.tw/catalog/view/theme/default/stylesheet/assets/images/favicon.png'
  },
  {
    url: 'http://taipeislpu.blogspot.com/',
    title: '新竹市語言治療師公會'
    // icon: 'http://taiwanslpu.org.tw/catalog/view/theme/default/stylesheet/assets/images/favicon.png'
  },
  {
    url: 'http://taipeislpu.blogspot.com/',
    title: '苗栗縣語言治療師公會'
    // icon: 'http://taiwanslpu.org.tw/catalog/view/theme/default/stylesheet/assets/images/favicon.png'
  },
  {
    url: 'http://taipeislpu.blogspot.com/',
    title: '台中市語言治療師公會'
    // icon: 'http://taiwanslpu.org.tw/catalog/view/theme/default/stylesheet/assets/images/favicon.png'
  }
]

const data1 = [
  '台灣聽力語言學會',
  '國立臺北健康護理大學聽語障礙科學研究所',
  '臺北市立教育大學教育學院語言治療碩士學位學程',
  '高雄師範大學聽力學與語言治療研究所',
  '中山醫學大學語言治療與聽力學系',
  '馬偕醫學院聽力暨語言治療學系',
  '亞洲大學聽力暨語言治療學系',
  '弘光科技大學語言治療與聽力學系',
  '中華醫事大學語言治療系'
]
</script>
