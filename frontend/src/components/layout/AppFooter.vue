<template>
  <footer class="bg-white border-t border-gray-200 mt-auto">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="py-12">
        <div class="grid grid-cols-1 md:grid-cols-4 gap-8">
          <!-- О сайте -->
          <div class="col-span-1 md:col-span-2">
            <div class="flex items-center space-x-2 mb-4">
              <div class="w-8 h-8 bg-blue-600 rounded-md flex items-center justify-center">
                <NewspaperIcon class="w-5 h-5 text-white" />
              </div>
              <span class="text-xl font-semibold text-gray-900">Post+</span>
            </div>
            <p class="text-sm text-gray-600 mb-4 max-w-md">
              Современная платформа для создания и чтения новостных статей. 
              Делитесь своими мыслями, обсуждайте актуальные темы и оставайтесь в курсе событий.
            </p>
            <div class="flex space-x-4">
              <a href="#" class="text-gray-400 hover:text-blue-600 transition-colors">
                <span class="sr-only">GitHub</span>
                <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.236 1.911 1.236 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
                </svg>
              </a>
            </div>
          </div>
          
          <!-- Навигация -->
          <div>
            <h3 class="text-sm font-semibold text-gray-900 tracking-wider uppercase mb-4">
              Навигация
            </h3>
            <ul class="space-y-3 text-sm">
              <li>
                <router-link
                  to="/"
                  class="text-gray-600 hover:text-blue-600 transition-colors"
                >
                  Главная
                </router-link>
              </li>
              <li>
                <router-link
                  to="/posts"
                  class="text-gray-600 hover:text-blue-600 transition-colors"
                >
                  Все посты
                </router-link>
              </li>
              <li>
                <router-link
                  to="/categories"
                  class="text-gray-600 hover:text-blue-600 transition-colors"
                >
                  Категории
                </router-link>
              </li>
              <li>
                <router-link
                  to="/posts/create"
                  class="text-gray-600 hover:text-blue-600 transition-colors"
                >
                  Создать пост
                </router-link>
              </li>
            </ul>
          </div>
          
          <!-- Ссылки -->
          <div>
            <h3 class="text-sm font-semibold text-gray-900 tracking-wider uppercase mb-4">
              Полезные ссылки
            </h3>
            <ul class="space-y-3 text-sm">
              <li>
                <a
                  href="#"
                  class="text-gray-600 hover:text-blue-600 transition-colors"
                >
                  О проекте
                </a>
              </li>
              <li>
                <a
                  href="#"
                  class="text-gray-600 hover:text-blue-600 transition-colors"
                >
                  Правила сообщества
                </a>
              </li>
              <li>
                <a
                  href="#"
                  class="text-gray-600 hover:text-blue-600 transition-colors"
                >
                  Политика конфиденциальности
                </a>
              </li>
              <li>
                <a
                  href="#"
                  class="text-gray-600 hover:text-blue-600 transition-colors"
                >
                  Обратная связь
                </a>
              </li>
            </ul>
          </div>
        </div>
      </div>
      
      <!-- Нижняя часть футера -->
      <div class="border-t border-gray-200 py-6">
        <div class="flex flex-col md:flex-row justify-between items-center">
          <div class="text-sm text-gray-600">
            © {{ currentYear }} Post+. Все права защищены.
          </div>
          <div class="flex items-center space-x-6 mt-4 md:mt-0 text-sm">
            <a
              href="#"
              class="text-gray-500 hover:text-blue-600 transition-colors"
            >
              Условия использования
            </a>
            <a
              href="#"
              class="text-gray-500 hover:text-blue-600 transition-colors"
            >
              Конфиденциальность
            </a>
            <button
              @click="scrollToTop"
              class="flex items-center space-x-1 text-gray-500 hover:text-blue-600 transition-colors"
            >
              <ArrowUpIcon class="w-4 h-4" />
              <span>Наверх</span>
            </button>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
import { computed } from 'vue'
import { NewspaperIcon, ArrowUpIcon } from '@heroicons/vue/24/outline'

export default {
  name: 'AppFooter',
  components: {
    NewspaperIcon,
    ArrowUpIcon
  },
  setup() {
    const currentYear = computed(() => new Date().getFullYear())
    
    const scrollToTop = () => {
      window.scrollTo({
        top: 0,
        behavior: 'smooth'
      })
    }
    
    return {
      currentYear,
      scrollToTop
    }
  }
}
</script>