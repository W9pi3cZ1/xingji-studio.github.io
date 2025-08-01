<script setup lang="ts">
import { ref } from 'vue'
import { useHead } from '@vueuse/head'

useHead({
  title: '星际工作室 | XINGJI Studio',
  meta: [
    {
      name: 'description',
      content: 'XINGJI工作室在2017年创立。由于我们都是学生，也就不需要支付大量工资费用，产品价格也大大降低。 \
在价格降低的同时，品质也不输大厂。我们保证我们的产品即便是免费的，也校验过每一项功能。即便我们没有校验出所有的问题，也会第一时间受理并修复任何人的报告。\
我们的技术也堪比大厂，例如我们发明的XRMU锁存器速度高达640Gbps！双通道更是高达1.2Tbps！遥摇领先DDR5！\
完全自主研发，内核使用XJ-Kernel 2.0，经过三次更新，UEFI引导方式，安全、可靠，并且完全免费（仅限于普通系列）',
    },
  ],
})

const products = ref([
  {
    title: '操作系统',
    description: 'XJ380操作系统，完全自主研发，内核使用XJ-Kernel 2.0，UEFI引导方式，安全、可靠',
    image: '/files/os.png',
    link: '/os/xj380'
  },
  {
    title: '星际云',
    description: '高速、稳定、安全的云服务平台',
    image: '/files/cloud.png',
    link: 'https://cloud.xingjisoft.top/'
  },
  {
    title: '软件产品',
    description: '高质量的软件解决方案',
    image: '/files/software.png',
    link: '/software'
  },
  {
    title: '游戏',
    description: '低价高质的游戏产品',
    image: '/files/games.png',
    link: '/software'
  }
])

const news_posts = ref([{
  title: 'XDC2025 推迟举行',
  image: '/xdc2025_black.png',
  description: '由于各项目开发进度落后于原计划、发布形式变更等原因，且为了留出足够时间用于打磨项目以给大家提供更完美稳定的产品（同时防止某些喷子\
因为XDC与项目正式发布日期不同步而喷人），经过商议，我们决定将XDC2025推迟至8月27日于线上举行（这是废话）。各位的支持就是我们更新的\
最大动力！希望大家能谅解！',
  more_text: '没有更多了',
  link: '#'
}, {
  title: 'XJ380 API手册现已公布',
  image: '/LOGO带底.png',
  description: '适用于XJ380操作系统的XJ380 API手册现已公布。开发工具将于稍后发布。请注意：该手册为测试版，可能与稍后发布的正式版有所出入。',
  more_text: '立刻开始“星际”之旅',
  link: '/os/xj380/download'
}, {
  title: '挖矿模拟器将迎来最后更新',
  image: '/software/bcms.png',
  description: '挖矿模拟器1.8.0 将于近期推出。本次更新将是挖矿模拟器的最后一次内容更新，之后我们将停止对挖矿模拟器的维护（这个破烂还有维护的必要吗（悲））。',
  more_text: '了解更多',
  link: '/news/2025031501'
}]);

const partners = ref([
  {
    name: '德沃洛普工作室',
    logo: '/files/develop_studio.png',
    link: 'http://pbhmjfsk.e.cn.vc/zh'
  },
  {
    name: '537工作室',
    logo: '/files/537logo.png',
    link: 'https://537studio.com/'
  },
  {
    name: 'PCC工作室',
    logo: '/files/pcc.png',
    link: 'https://pcc.xingjisoft.top/'
  },
  {
    name: '星际云',
    logo: '/files/XINGJI Cloud.png',
    link: 'https://cloud.xingjisoft.top/'
  }
])

const news = ref({
  title: '预告片 1',
  subtitle: 'XINGJI 2025 开发者大会',
  link: 'https://www.bilibili.com/video/BV1xcjEzpEh7/',
  image: {
    src: '/primage.png',
    alt: '宣传图',
  },
});

</script>

<template>
  <div class="min-h-screen bg-gradient-to-br from-gray-900 via-gray-800 to-gray-900">
    <!-- News Section -->
    <div class="pt-16 relative">
      <!-- News Background Image -->
      <div class="news-bg-container">
        <!-- <img :src="news.image.src" :alt="news.image.alt" class="image">
        <div class="overlay"></div> -->
      </div>
      <div class="news-container">
        <div class="cover">
          <img :src="news.image.src" :alt="news.image.alt" class="image">
        </div>
        <div class="body">
          <div class="container">
            <h1 class="title">
              {{ news.title }}
            </h1>
            <p class="subtitle">
              {{ news.subtitle }}
            </p>
          </div>
          <a :href="news.link" class="link-button text-white">立刻观看预告片</a>
        </div>
      </div>
    </div>

    <!-- Products Section -->
    <section class="py-12 px-4 relative">
      <div class="max-w-7xl mx-auto">
        <h2 class="text-4xl font-bold text-white mb-6 px-6">我们的产品及服务</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
          <div v-for="product in products" :key="product.title" class="group relative">
            <div
              class="absolute inset-0 rounded-2xl bg-gradient-to-r from-blue-500 to-purple-500 opacity-0 group-hover:opacity-100 transition-opacity duration-300 -z-10 blur">
            </div>
            <div class="relative bg-gray-800/50 backdrop-blur-md rounded-2xl p-6 group h-full flex flex-col">
              <div>
                <div class="w-full h-48 rounded mb-4 bg-gray-50 overflow-hidden">
                  <img :src="product.image" :alt="product.title"
                    class="w-full h-full object-contain transition-all duration-300">
                </div>
                <h3 class="text-xl font-bold text-white mb-2">{{ product.title }}</h3>
                <p class="text-gray-400 mb-4">{{ product.description }}</p>
              </div>

              <a :href="product.link"
                class="inline-flex items-center text-blue-400 fill-blue-400 hover:text-blue-300 hover:fill-blue-300 transition-all duration-200 leading-4">
                <span>了解更多</span>
                <svg class="w-4 h-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 512">
                  <path
                    d="M278.6 233.4c12.5 12.5 12.5 32.8 0 45.3l-160 160c-12.5 12.5-32.8 12.5-45.3 0s-12.5-32.8 0-45.3L210.7 256 73.4 118.6c-12.5-12.5-12.5-32.8 0-45.3s32.8-12.5 45.3 0l160 160z" />
                </svg>
              </a>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="py-12 px-4 relative">
      <div class="max-w-7xl mx-auto">
        <h2 class="text-4xl font-bold text-white mb-6 px-6">近期新闻</h2>
        <div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
          <div v-for="post in news_posts" class="bg-gray-800/50 backdrop-blur-md rounded-2xl p-6">
            <div class="w-full h-48 rounded mb-4 bg-gray-50 overflow-hidden">
              <img :src="post.image" alt="" class="w-full h-full object-contain transition-all duration-300">
            </div>
            <h3 class="text-xl font-bold text-white mb-4">{{ post.title }}</h3>
            <p class="text-gray-400 mb-4">
              {{ post.description }}
            </p>
            <a :href="post.link"
              class="inline-flex items-center text-blue-400 fill-blue-400 hover:text-blue-300 hover:fill-blue-300 transition-all duration-200 leading-4">
              <span>{{ post.more_text }}</span>
              <svg class="w-4 h-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 512">
                <path
                  d="M278.6 233.4c12.5 12.5 12.5 32.8 0 45.3l-160 160c-12.5 12.5-32.8 12.5-45.3 0s-12.5-32.8 0-45.3L210.7 256 73.4 118.6c-12.5-12.5-12.5-32.8 0-45.3s32.8-12.5 45.3 0l160 160z" />
              </svg>
            </a>
          </div>
        </div>
      </div>
    </section>

    <!-- Advantages Section -->
    <section class="py-12 px-4 relative">
      <div class="max-w-7xl mx-auto">
        <h2 class="text-4xl font-bold text-white mb-6 px-6">我们有什么优势？</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
          <div class="bg-gray-800/50 backdrop-blur-md rounded-2xl p-6">
            <h3 class="text-xl font-bold text-white mb-4">学生团队，低成本优势</h3>
            <p class="text-gray-400">
              XINGJI工作室在2017年创立。由于我们都是学生，也就不需要支付大量工资费用，产品价格也大大降低。
            </p>
          </div>
          <div class="bg-gray-800/50 backdrop-blur-md rounded-2xl p-6">
            <h3 class="text-xl font-bold text-white mb-4">品质保证</h3>
            <p class="text-gray-400">
              在价格降低的同时，品质也不输大厂。我们保证我们的产品即便是免费的，也校验过每一项功能。即便我们没有校验出所有的问题，也会第一时间受理并修复任何人的报告。
            </p>
          </div>
          <div class="bg-gray-800/50 backdrop-blur-md rounded-2xl p-6">
            <h3 class="text-xl font-bold text-white mb-4">技术创新</h3>
            <p class="text-gray-400">
              我们的技术也堪比大厂，例如我们发明的XRMU锁存器速度高达640Gbps！双通道更是高达1.2Tbps！遥摇领先DDR5！
            </p>
          </div>
          <div class="bg-gray-800/50 backdrop-blur-md rounded-2xl p-6">
            <h3 class="text-xl font-bold text-white mb-4">XJ380操作系统</h3>
            <p class="text-gray-400">
              完全自主研发，内核使用XJ-Kernel 2.0，经过三次更新，UEFI引导方式，安全、可靠，并且完全免费（仅限于普通系列）
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- Partners Section -->
    <section class="py-12 px-4 relative">
      <div class="max-w-7xl mx-auto px-6">
        <h2 class="text-4xl font-bold text-white mb-6">我们的合作伙伴</h2>
        <div class="grid grid-cols-2 md:grid-cols-4 gap-8">
          <a v-for="partner in partners" :key="partner.name" :href="partner.link"
            class="group relative bg-gray-800/50 backdrop-blur-md rounded-2xl p-6 hover:transform hover:scale-[1.02] transition-all duration-300">
            <div
              class="absolute inset-0 rounded-2xl bg-gray-700/50 opacity-0 group-hover:opacity-100 transition-opacity duration-300 -z-10">
            </div>
            <img :src="partner.logo" :alt="partner.name" class="w-full h-auto">
          </a>
        </div>
      </div>
    </section>

    <footer class="py-8 text-center text-white bg-gray-800/50 backdrop-blur-md">
      <p class="text-xl font-semibold">
        我们保证您所投入的每一分钱都会被我们用于有意义的事上！
      </p>
    </footer>
  </div>
</template>