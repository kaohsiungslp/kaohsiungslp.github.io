<template>
  <div
    class="grid grid-cols-1 gap-10 md:grid-cols-2 md:gap-x-4 md:gap-y-10 mx-[5vw]"
  >
    <div class="card bg-base-100 shadow-xl">
      <div class="card-body">
        <h2 class="card-title text-primary">最新消息</h2>
        <div class="overflow-x-auto">
          <table class="table table-zebra">
            <tbody>
              <!-- row 1 -->
              <tr
                v-for="(item, index) in news"
                :class="`hover:bg-sky-100  ${
                  index % 2 == 0 ? 'bg-white' : 'bg-slate-100'
                }`"
              >
                <td>
                  <div class="tooltip tooltip-primary z-99" data-tip="前往網站">
                    <a> {{ item }}</a>
                  </div>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
      <div class="btn absolute -bottom-6 right-6 btn-primary border-none">
        更多消息<span class="material-symbols-outlined"> read_more </span>
      </div>
    </div>

    <div class="card bg-base-100 shadow-xl">
      <div class="card-body">
        <h2 class="card-title text-primary">研習活動</h2>
        <div class="overflow-x-auto">
          <table class="table table-zebra">
            <tbody>
              <!-- row 1 -->
              <tr v-for="(item, index) in activities">
                <td>
                  <div class="tooltip tooltip-primary z-99" data-tip="前往網站">
                    <a href=""> {{ item }}</a>
                  </div>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
      <div class="btn absolute -bottom-6 right-6 btn-primary border-none">
        更多活動<span class="material-symbols-outlined"> read_more </span>
      </div>
    </div>

    <button
      class="btn btn-secondary fixed right-0 w-[20px] h-32"
      onclick="my_modal_5.showModal()"
    >
      我要入會
      <span class="material-symbols-outlined"> home </span>
    </button>
    <dialog id="my_modal_5" class="modal modal-bottom sm:modal-middle">
      <div class="modal-box">
        <h3 class="font-bold text-lg text-secondary">入會表單</h3>
        <MailFrom />
        <div class="modal-action">
          <form method="dialog">
            <button class="btn btn-secondary mr-2">送出</button>
            <button class="btn btn-ghost">取消</button>
          </form>
        </div>
      </div>
    </dialog>
  </div>
</template>

<script setup>
import MailFrom from '../components/mailForm.vue'
const news = [
  '研習課程 - 聽損者的生命經驗與醫療科技工作坊',
  '研習課程 - 2024_咀嚼吞嚥障礙口腔衛生照護工作坊',
  '衛生福利部補助醫事人員至原住民地區開業補助案',
  '徵才 - 楠梓家教',
  '研習課程 - 2024年4月14日『閱讀障礙研究新知與語法分析介入』',
  '研習課程 - 聽損者的生命經驗與醫療科技工作坊',
  '研習課程 - 2024_咀嚼吞嚥障礙口腔衛生照護工作坊',
  '衛生福利部補助醫事人員至原住民地區開業補助案',
  '徵才 - 楠梓家教',
  '研習課程 - 2024年4月14日『閱讀障礙研究新知與語法分析介入』'
]

const activities = [
  '研習課程 - 聽損者的生命經驗與醫療科技工作坊',
  '研習課程 - 2024_咀嚼吞嚥障礙口腔衛生照護工作坊',
  '研習課程 - 2024年4月14日『閱讀障礙研究新知與語法分析介入』',
  '錄取名單 - Verbal Motor Learning 治療法簡介與臨床經驗分享',
  '課程資訊 - 兒童我的優勢卡專業人員初階培訓',
  '研習課程 - 聽損者的生命經驗與醫療科技工作坊',
  '研習課程 - 2024_咀嚼吞嚥障礙口腔衛生照護工作坊',
  '研習課程 - 2024年4月14日『閱讀障礙研究新知與語法分析介入』',
  '錄取名單 - Verbal Motor Learning 治療法簡介與臨床經驗分享',
  '課程資訊 - 兒童我的優勢卡專業人員初階培訓'
]
</script>
