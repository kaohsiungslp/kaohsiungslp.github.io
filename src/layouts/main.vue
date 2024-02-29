<template>
  <div class="navbar bg-base-100 z-99">
    <div class="navbar-start">
      <div class="dropdown">
        <div tabindex="0" role="button" class="btn btn-ghost lg:hidden">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-5 w-5"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 6h16M4 12h8m-8 6h16"
            />
          </svg>
        </div>
        <ul
          tabindex="0"
          class="menu menu-sm dropdown-content mt-3 z-[1] p-2 shadow bg-base-100 rounded-box w-52"
        >
          <li><a>Item 1</a></li>
          <li>
            <a>Parent</a>
            <ul class="p-2">
              <li><a>Submenu 1</a></li>
              <li><a>Submenu 2</a></li>
            </ul>
          </li>
          <li><a>Item 3</a></li>
        </ul>
      </div>
      <img class="h-[50px] mx-2" src="../assets/logo.png" />
      <a class="text-md text-primary font-semibold min-w-fit"
        >社團法人<br />高雄市語言治療師公會</a
      >
    </div>
    <div class="navbar-center hidden z-99 lg:flex">
      <ul class="menu menu-horizontal px-1">
        <li v-for="(item, i) in menu">
          <template
            v-if="item.children?.length === 0 || item.children === undefined"
          >
            <a>{{ item.label }}</a>
          </template>
          <template v-else>
            <!-- 看要不要改menu https://daisyui.com/components/menu/ -->
            <details :class="`${i === menu.length - 1 ? ' dropdown-end' : ''}`">
              <summary @click="openItem = item.label">{{ item.label }}</summary>
              <ul
                v-if="openItem == item.label"
                class="z-50 dropdown-content card card-compact p-2 shadow bg-primary text-primary-content"
              >
                <li v-for="child in item.children" class="w-max">
                  <a>{{ child.label }}</a>
                </li>
              </ul>
            </details>
          </template>
        </li>
      </ul>
    </div>
  </div>
</template>
<script setup lang="ts">
import { ref } from 'vue'

const openItem = ref('')
const menu = [
  {
    label: '會員專區',
    children: [
      {
        label: '申請公會證明'
      },
      {
        label: '醫事人員執業、歇業等登記說明'
      },
      {
        label: '會員福利補助及特約商店'
      },
      {
        label: '活動消息及剪影'
      }
    ]
  },
  {
    label: '最新消息',
    children: [
      {
        label: '公文公告'
      },
      {
        label: '公會章程'
      },
      {
        label: '會務人員'
      }
    ]
  },
  {
    label: '會務及會議資料',
    children: [
      {
        label: '理監事會議記錄'
      },
      {
        label: '會員大會會議記錄'
      },
      {
        label: '語言治療師法'
      },
      {
        label: '公會部落格'
      },
      {
        label: '相關法規資料'
      },
      {
        label: '語言治療所設置標準'
      }
    ]
  },
  {
    label: '研習課程'
  },
  {
    label: '徵才資訊'
  },
  {
    label: '聯絡我們',
    children: [
      {
        label: 'Facebook'
      },
      {
        label: '公會信箱'
      },
      {
        label: '@line'
      }
    ]
  },
  {
    label: '外部連結',
    children: [
      {
        label: '長照'
      },
      {
        label: '高雄市社會局早療補助'
      },
      {
        label: '中華民國語言治療師公會全國聯合會'
      },
      {
        label: '台灣聽力語言學會'
      }
    ]
  }
]
</script>
