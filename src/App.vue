// LandingPage.vue
<script setup>
import { ref } from 'vue'
import { 
  Wallet, 
  CreditCard, 
  PieChart, 
  Shield, 
  ArrowUpRight,
  Smartphone,
  Users,
  CheckCircle
} from 'lucide-vue-next'

const features = [
  {
    icon: Wallet,
    title: 'Digital Wallet',
    description: 'Manage all your payments and transfers in one secure place with our state-of-the-art digital wallet.'
  },
  {
    icon: CreditCard,
    title: 'Virtual Cards',
    description: 'Create virtual cards instantly for safer online shopping and better spending control.'
  },
  {
    icon: PieChart,
    title: 'Smart Analytics',
    description: 'Track your spending patterns and get personalized insights to make better financial decisions.'
  },
  {
    icon: Shield,
    title: 'Bank-Grade Security',
    description: 'Your money is protected with industry-leading security measures and encryption.'
  }
]

const stats = ref([
  { value: '2M+', label: 'Active Users' },
  { value: '150+', label: 'Countries' },
  { value: '$500M', label: 'Transactions Daily' },
  { value: '99.99%', label: 'Uptime' }
])
</script>

<template>
  <div class="min-h-screen bg-white">
    <!-- Navigation -->
    <nav class="bg-white border-b">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between h-16 items-center">
          <div class="flex-shrink-0">
            <span class="text-2xl font-bold text-[#cf173c]">PayFlow</span>
          </div>
          <div class="hidden md:block">
            <div class="flex space-x-8">
              <a href="#" class="text-gray-700 hover:text-[#cf173c] px-3 py-2">Features</a>
              <a href="#" class="text-gray-700 hover:text-[#cf173c] px-3 py-2">Pricing</a>
              <a href="#" class="text-gray-700 hover:text-[#cf173c] px-3 py-2">About</a>
              <a href="#" class="text-gray-700 hover:text-[#cf173c] px-3 py-2">Contact</a>
            </div>
          </div>
          <div class="flex items-center space-x-4">
            <button class="text-gray-700 hover:text-[#cf173c] px-3 py-2">Sign In</button>
            <button class="bg-[#cf173c] text-white px-4 py-2 rounded-lg hover:bg-[#bf062c] transition-colors">
              Get Started
            </button>
          </div>
        </div>
      </div>
    </nav>

    <!-- Hero Section -->
    <div class="relative bg-white overflow-hidden">
      <div class="max-w-7xl mx-auto">
        <div class="relative z-10 pb-8 bg-white sm:pb-16 md:pb-20 lg:pb-28 xl:pb-32">
          <main class="mt-10 mx-auto max-w-7xl px-4 sm:mt-12 sm:px-6 md:mt-16 lg:mt-20 lg:px-8 xl:mt-28">
            <div class="sm:text-center lg:text-left">
              <h1 class="text-4xl tracking-tight font-extrabold text-gray-900 sm:text-5xl md:text-6xl">
                <span class="block">The Future of</span>
                <span class="block text-[#cf173c]">Digital Payments</span>
              </h1>
              <p class="mt-3 text-base text-gray-500 sm:mt-5 sm:text-lg sm:max-w-xl sm:mx-auto md:mt-5 md:text-xl lg:mx-0">
                Transform the way you handle money with our next-generation mobile wallet. 
                Send, receive, and manage your finances with unmatched security and convenience.
              </p>
              <div class="mt-5 sm:mt-8 sm:flex sm:justify-center lg:justify-start">
                <div class="rounded-md shadow">
                  <a href="#" class="w-full flex items-center justify-center px-8 py-3 border border-transparent 
                    text-base font-medium rounded-md text-white bg-[#cf173c] hover:bg-[#bf062c] md:py-4 md:text-lg md:px-10">
                    Download App
                  </a>
                </div>
                <div class="mt-3 sm:mt-0 sm:ml-3">
                  <a href="#" class="w-full flex items-center justify-center px-8 py-3 border border-transparent 
                    text-base font-medium rounded-md text-[#cf173c] bg-white border-[#cf173c] hover:bg-gray-50 
                    md:py-4 md:text-lg md:px-10">
                    Learn More
                  </a>
                </div>
              </div>
            </div>
          </main>
        </div>
      </div>
    </div>

    <!-- Features Section -->
    <div class="py-12 bg-gray-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center">
          <h2 class="text-3xl font-extrabold text-gray-900 sm:text-4xl">
            Everything you need in a modern wallet
          </h2>
          <p class="mt-4 max-w-2xl text-xl text-gray-500 mx-auto">
            Discover why millions choose PayFlow for their digital finance needs.
          </p>
        </div>

        <div class="mt-10">
          <div class="grid grid-cols-1 gap-8 sm:grid-cols-2 lg:grid-cols-4">
            <div v-for="feature in features" :key="feature.title" 
              class="relative group bg-white p-6 rounded-lg shadow-sm hover:shadow-md transition-shadow">
              <div>
                <span class="inline-flex items-center justify-center p-3 bg-[#cf173c] bg-opacity-10 rounded-md">
                  <component :is="feature.icon" 
                    class="h-6 w-6 text-[#cf173c]" />
                </span>
              </div>
              <div class="mt-4">
                <h3 class="text-lg font-medium text-gray-900 group-hover:text-[#cf173c] transition-colors">
                  {{ feature.title }}
                </h3>
                <p class="mt-2 text-base text-gray-500">
                  {{ feature.description }}
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Stats Section -->
    <div class="bg-[#cf173c]">
      <div class="max-w-7xl mx-auto py-12 px-4 sm:py-16 sm:px-6 lg:px-8">
        <div class="grid grid-cols-2 gap-4 md:grid-cols-4">
          <div v-for="stat in stats" :key="stat.label" class="text-center">
            <p class="text-3xl font-extrabold text-white">{{ stat.value }}</p>
            <p class="mt-1 text-base text-white opacity-80">{{ stat.label }}</p>
          </div>
        </div>
      </div>
    </div>

    <!-- CTA Section -->
    <div class="bg-gray-50">
      <div class="max-w-7xl mx-auto py-12 px-4 sm:px-6 lg:px-8">
        <div class="bg-[#cf173c] rounded-lg shadow-xl overflow-hidden">
          <div class="pt-10 pb-12 px-6 sm:pt-16 sm:px-16 lg:py-16 lg:pr-0 xl:py-20 xl:px-20">
            <div class="lg:self-center">
              <h2 class="text-3xl font-extrabold text-white sm:text-4xl">
                <span class="block">Ready to get started?</span>
                <span class="block">Download PayFlow today.</span>
              </h2>
              <p class="mt-4 text-lg leading-6 text-white opacity-90">
                Join millions of users who trust PayFlow for their digital finance needs.
                Get started in minutes with our simple setup process.
              </p>
              <a href="#" class="mt-8 bg-white border border-transparent rounded-md shadow px-6 py-3 inline-flex 
                items-center text-base font-medium text-[#cf173c] hover:bg-gray-50">
                Download Now
                <ArrowUpRight class="ml-2 h-5 w-5" />
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Footer -->
    <footer class="bg-gray-900">
      <div class="max-w-7xl mx-auto py-12 px-4 sm:px-6 lg:px-8">
        <div class="grid grid-cols-2 md:grid-cols-4 gap-8">
          <div>
            <h3 class="text-sm font-semibold text-gray-400 tracking-wider uppercase">Product</h3>
            <ul class="mt-4 space-y-4">
              <li><a href="#" class="text-base text-gray-300 hover:text-white">Features</a></li>
              <li><a href="#" class="text-base text-gray-300 hover:text-white">Security</a></li>
              <li><a href="#" class="text-base text-gray-300 hover:text-white">Business</a></li>
              <li><a href="#" class="text-base text-gray-300 hover:text-white">Enterprise</a></li>
            </ul>
          </div>
          <div>
            <h3 class="text-sm font-semibold text-gray-400 tracking-wider uppercase">Company</h3>
            <ul class="mt-4 space-y-4">
              <li><a href="#" class="text-base text-gray-300 hover:text-white">About</a></li>
              <li><a href="#" class="text-base text-gray-300 hover:text-white">Blog</a></li>
              <li><a href="#" class="text-base text-gray-300 hover:text-white">Careers</a></li>
              <li><a href="#" class="text-base text-gray-300 hover:text-white">Press</a></li>
            </ul>
          </div>
          <div>
            <h3 class="text-sm font-semibold text-gray-400 tracking-wider uppercase">Resources</h3>
            <ul class="mt-4 space-y-4">
              <li><a href="#" class="text-base text-gray-300 hover:text-white">Documentation</a></li>
              <li><a href="#" class="text-base text-gray-300 hover:text-white">Help Center</a></li>
              <li><a href="#" class="text-base text-gray-300 hover:text-white">API Status</a></li>
              <li><a href="#" class="text-base text-gray-300 hover:text-white">Support</a></li>
            </ul>
          </div>
          <div>
            <h3 class="text-sm font-semibold text-gray-400 tracking-wider uppercase">Legal</h3>
            <ul class="mt-4 space-y-4">
              <li><a href="#" class="text-base text-gray-300 hover:text-white">Privacy</a></li>
              <li><a href="#" class="text-base text-gray-300 hover:text-white">Terms</a></li>
              <li><a href="#" class="text-base text-gray-300 hover:text-white">Cookie Policy</a></li>
              <li><a href="#" class="text-base text-gray-300 hover:text-white">Licenses</a></li>
            </ul>
          </div>
        </div>
        <div class="mt-8 border-t border-gray-700 pt-8 md:flex md:items-center md:justify-between">
          <div class="flex space-x-6 md:order-2">
            <a href="#" class="text-gray-400 hover:text-gray-300">
              <span class="sr-only">Facebook</span>
              <svg class="h-6 w-6" fill="currentColor" viewBox="0 0 24 24">
                <path fill-rule="evenodd" d="M22 12c0-5.523-4.477-10-10-10S2 6.477 2 12c0 4.991 3.657 9.128 8.438 9.878v-6.987h-2.54V12h2.54V9.797c0-2.506 1.492-3.89 3.777-3.89 1.094 0 2.238.195 2.238.195v2.46h-1.26c-1.243 0-1.63.771-1.63 1.562V12h2.773l-.443 2.89h-2.33v6.988C18.343 21.128 22 16.991 22 12z" clip-rule="evenodd" />
              </svg>
            </a>
            <a href="#" class="text-gray-400 hover:text-gray-300">
              <span class="sr-only">Twitter</span>
              <svg class="h-6 w-6" fill="currentColor" viewBox="0 0 24 24">
                <path d="M8.29 20.251c7.547 0 11.675-6.253 11.675-11.675 0-.178 0-.355-.012-.53A8.348 8.348 0 0022 5.92a8.19 8.19 0 01-2.357.646 4.118 4.118 0 001.804-2.27 8.224 8.224 0 01-2.605.996 4.107 4.107 0 00-6.993 3.743 11.65 11.65 0 01-8.457-4.287 4.106 4.106 0 001.27 5.477A4.072 4.072 0 012.8 9.713v.052a4.105 4.105 0 003.292 4.022 4.095 4.095 0 01-1.853.07 4.108 4.108 0 003.834 2.85A8.233 8.233 0 012 18.407a11.616 11.616 0 006.29 1.84" />
              </svg>
            </a>
            <a href="#" class="text-gray-400 hover:text-gray-300">
              <span class="sr-only">LinkedIn</span>
              <svg class="h-6 w-6" fill="currentColor" viewBox="0 0 24 24">
                <path fill-rule="evenodd" d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z" clip-rule="evenodd" />
              </svg>
            </a>
            <a href="#" class="text-gray-400 hover:text-gray-300">
              <span class="sr-only">GitHub</span>
              <svg class="h-6 w-6" fill="currentColor" viewBox="0 0 24 24">
                <path fill-rule="evenodd" d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z" clip-rule="evenodd" />
              </svg>
            </a>
          </div>
          <div class="mt-8 md:mt-0 md:order-1">
            <p class="text-center text-base text-gray-400">
              &copy; 2024 PayFlow, Inc. All rights reserved.
            </p>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>