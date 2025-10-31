<template>
    <div class="relative overflow-hidden bg-linear-to-br from-gray-900 to-gray-800
        text-white py-12 px-4 sm:py-16 md:py-20 md:px-12 lg:px-20">
        <div class="max-w-7xl mx-auto">
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8 md:gap-12 mb-12">
                <div class="space-y-6">
                    <div class="flex items-center text-xl sm:text-2xl font-bold">
                        <div class="w-8 h-8 sm:w-10 sm:h-10 flex items-center justify-center rounded-full border-3 sm:border-4
                            border-pink-600 text-pink-600 mr-2">P</div>
                        <span>anda <span class="text-yellow-500">Services</span></span>
                    </div>
                    <p class="text-gray-300 leading-relaxed">
                        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Earum sed harum neque, 
                        reiciendis quia amet! Non sequi expedita ad, inventore maiores animi assumenda 
                        soluta sit, est, reiciendis blanditiis dolorum. Corporis.
                    </p>
                    <div class="flex gap-4">
                        <a v-for="(social, index) in socialLinks" :key="index" :href="social.href"
                            target="_blank" rel="noopener noreferrer"
                            :class="`w-10 h-10 rounded-full bg-gray-700 flex items-center justify-center
                            ${social.hoverColor} transition-colors`">
                            <component :is="social.icon" class="w-6 h-6" />
                        </a>
                    </div>
                </div>

                <div class="space-y-6">
                    <h3 class="text-xl font-semibold border-b-2 border-pink-600 pb-2 inline-block">Quick Links</h3>
                    <ul class="space-y-3 text-gray-300">
                        <li><a href="#home" class="hover:text-pink-500 transition-colors">Home</a></li>
                        <li><a href="#about" class="hover:text-pink-500 transition-colors">About Us</a></li>
                        <li><a href="#service" class="hover:text-pink-500 transition-colors">Services</a></li>
                        <li><a href="#contact" class="hover:text-pink-500 transition-colors">Contact</a></li>
                    </ul>
                </div>

                <div class="space-y-6">
                    <h3 class="text-xl font-semibold border-b-2 border-pink-600 pb-2 inline-block">Our Services</h3>
                    <ul class="space-y-3 text-gray-300">
                        <li><a href="#" class="hover:text-pink-500 transition-colors">UI/UX Design</a></li>
                        <li><a href="#" class="hover:text-pink-500 transition-colors">Development</a></li>
                        <li><a href="#" class="hover:text-pink-500 transition-colors">Marketing</a></li>
                        <li><a href="#" class="hover:text-pink-500 transition-colors">Business Branding</a></li>
                        <li><a href="#" class="hover:text-pink-500 transition-colors">Photography</a></li>
                    </ul>
                </div>

                <!-- Subscription -->
                <div class="space-y-6">
                    <h3 class="text-xl font-semibold border-b-2 border-pink-600 pb-2 inline-block">Subscribe</h3>
                    <p class="text-gray-300 leading-relaxed">
                        Subscribe to our newsletter to get the latest updates and offers.
                    </p>
                    <form class="flex flex-col sm:flex-row gap-3">
                        <input type="email" placeholder="Enter your email"
                            class="w-full bg-gray-800 border border-pink-600 px-4 py-3 rounded-lg focus:ring-2 focus:ring-pink-500
                            focus:border-transparent transition-all focus:outline-none text-gray-300" />
                        <button type="submit"
                            class="bg-pink-500 px-6 py-3 rounded-lg text-white font-medium hover:bg-pink-600 transition-colors">
                            <!-- Icon -->
                            <Send class="w-5 h-5 inline-block" />
                        </button>
                    </form>
                </div>
            </div>
        </div>
    </div>
</template>
<script setup>
import { Facebook, Instagram, Linkedin, Send, Twitter } from 'lucide-vue-next';

const socialLinks = [
    { icon: Facebook, href: 'https://facebook.com', hoverColor: 'hover:bg-blue-600' },
    { icon: Twitter, href: 'https://twitter.com', hoverColor: 'hover:bg-blue-400' },
    { icon: Linkedin, href: 'https://linkedin.com', hoverColor: 'hover:bg-blue-700' },
    { icon: Instagram, href: 'https://instagram.com', hoverColor: 'hover:bg-pink-500' },
];
</script>