<template>
    <nav class="fixed w-full bg-gray-50 left-0 right-0 z-50">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 md:px-12 lg:px-20 py-3 md:py-4 flex items-center justify-between">
            <!-- Logo -->
             <div class="flex items-center text-xl sm:text-2xl font-bold text-gray-900">
                <div class="w-8 h-8 sm:w-10 sm:h-10 flex items-center justify-center rounded-full border-3 sm:border-4
                    border-pink-600 text-pink-600 mr-2">P</div>
                <span>anda <span class="text-yellow-500">Services</span></span>
             </div>

            <!-- Links -->
             <ul class="hidden md:flex items-center gap-6 lg:gap-8 text-gray-700 font-medium">
                <li v-for="item in menuItems" :key="item.name"
                    class="hover:text-green-500 cursor-pointer transition-colors">
                    <a :href="item.path">{{ item.name }}</a>
                </li>
             </ul>

            <!-- Button -->
             <div class="hidden md:block">
                <button class="px-4 py-2 sm:px-5 sm:py-2 rounded-lg bg-pink-500 text-white 
                    font-medium hover:bg-pink-600 transition-colors">Get Started</button>
             </div>

            <!-- Mobile menu icon -->
             <div class="md:hidden">
                <button @click="toggleMenu" class="p-1 rounded-md focus:outline-none focus:ring-2 focus:ring-pink-500">
                    <component 
                        :is="isMenuOpen ? X : Menu"
                        class="w-6 h-6 text-gray-700"
                    />
                </button>
             </div>
            
        </div>

        <!-- Mobile menu -->
        <div v-if="isMenuOpen"
            class="md:hidden bg-white shadow-lg border-t border-gray-200">
            <div class="px-4 py-3 space-y-3">
                <a v-for="item in menuItems"
                    :key="item.name"
                    :href="item.path"
                    class="block py-2 px-4 text-gray-700 hover:bg-gray-100 rounded-lg hover:text-green-500 transition-colors">
                    {{ item.name }}
                </a>
                <div class="pt-2">
                    <button class="w-full py-2 rounded-lg bg-pink-500 text-white font-medium hover:bg-pink-600 transition-colors">
                        Get Started
                    </button>
                </div>
            </div>
        </div>
    </nav>
</template>
<script setup>
import { ref } from 'vue';
import { X, Menu } from 'lucide-vue-next';

const isMenuOpen = ref(false);

const toggleMenu = () => {
    isMenuOpen.value = !isMenuOpen.value;
}

const menuItems = [
    {name: 'Home', path: '#'},
    {name: 'About', path: '#about'},
    {name: 'Company', path: '#company'},
    {name: 'Services', path: '#service'},
    {name: 'Contact', path: '#contact'}
];
</script>