<template>
    <section id="contact" class="relative overflow-hidden bg-linear-to-br from-blue-50 to-purple-50
        py-12 px-4 sm:py-16 md:py-20 md:px-12 lg:px-20">
        <div class="max-w-7xl mx-auto">
            <div class="flex flex-col items-center justify-center text-center mb-10" data-aos="fade-down">
                <div class="max-w-2xl space-y-6">
                    <h2 class="text-4xl sm:text-5xl text-gray-900">
                        Get In 
                        <span class="font-bold text-black">Touch</span> 
                        <span class="text-green-500">.</span>
                    </h2>
                    <div class="flex gap-3 mt-4 justify-center">
                        <Circle class="text-pink-500 w-5 h-5" />
                        <Circle class="text-yellow-500 w-5 h-5" />
                        <Circle class="text-green-500 w-5 h-5" />
                    </div>
                </div>
            </div>

            <div class="flex flex-col lg:flex-row gap-8 md:gap-12 items-center">
                <div class="bg-white flex-1 rounded-2xl md:rounded-3xl shadow-lg md:shadow-xl p-6 sm:p-8 border border-gray-100"
                    data-aos="fade-right" data-aos-delay="100">
                    <form action="">
                        <div data-aos="fade-up" data-aos-delay="150" class="mb-6">
                            <label for="name" class="block text-sm font-medium text-gray-700 mb-2">Full Name</label>
                            <input type="text" id="name" placeholder="Enter your full name"
                                class="w-full border border-gray-300 px-4 py-3 rounded-lg focus:ring-2 focus:ring-pink-500
                                focus:border-transparent transition-all focus:outline-none" />
                        </div>
                        <div data-aos="fade-up" data-aos-delay="200" class="mb-6">
                            <label for="email" class="block text-sm font-medium text-gray-700 mb-2">Email Address</label>
                            <input type="email" id="email" placeholder="Enter your email address"
                                class="w-full border border-gray-300 px-4 py-3 rounded-lg focus:ring-2 focus:ring-pink-500
                                focus:border-transparent transition-all focus:outline-none" />
                        </div>
                        <div data-aos="fade-up" data-aos-delay="250" class="mb-6">
                            <label for="message" class="block text-sm font-medium text-gray-700 mb-2">Message</label>
                            <textarea id="message" rows="4" placeholder="Enter your message"
                                class="w-full border border-gray-300 px-4 py-3 rounded-lg focus:ring-2 focus:ring-pink-500
                                focus:border-transparent transition-all focus:outline-none"></textarea>
                        </div>
                        <div data-aos="fade-up" data-aos-delay="300">
                            <button class="bg-pink-500 px-6 py-3 sm:px-8 sm:py-4 shadow-md rounded-lg text-white font-medium 
                                    hover:shadow-lg transition-all flex items-center justify-center gap-2 text-sm sm:text-base w-full">
                                Send Message
                                <Send class="w-5 h-5 ml-2 inline-block" />
                            </button>
                        </div>
                    </form>
                </div>

                <div class="flex-1 flex flex-col items-center lg:items-start">
                    <div class="w-full max-w-md h-64 sm:h-72 md:h-80 overflow-hidden shadow-lg 
                        rounded-lg md:rounded-2xl mb-8" data-aos="fade-left" data-aos-delay="100">
                        <img src="/contact.jpg" alt="contact us" class="w-full h-full object-cover transform hover:scale-105
                            transition-all duration-500 ease-in-out" />
                    </div>
                    <div class="space-y-4 w-full max-w-md">
                        <div v-for="(contact, index) in contactInfo" :key="index"
                            class="flex items-center gap-4 p-4 bg-white rounded-xl shadow-md"
                            :data-aos="contact.aos" :data-aos-delay="contact.delay">
                            <div :class="`w-12 h-12 ${contact.bgColor} rounded-lg flex items-center justify-center`">
                                <component :is="contact.icon" :class="`w-6 h-6 ${contact.iconColor}`"/>
                            </div>
                            <div>
                                <h3 class="font-semibold text-gray-800">{{ contact.title }}</h3>
                                <p class="text-gray-600">{{ contact.detail }}</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <div class="absolute bottom-20 left-10 border-4 w-16 h-16 sm:w-20 sm:h-20 md:w-24 md:h-24
            rounded-full border-pink-500 hidden md:block" data-aos="zoom-in" data-aos-delay="600"></div>
        <div class="absolute top-40 right-10 border-4 w-20 h-20 sm:w-24 sm:h-24 md:w-28 md:h-28
            rounded-full border-purple-500 opacity-50 hidden md:block" data-aos="zoom-in" data-aos-delay="600"></div>
    </section>
</template>
<script setup>
import { Circle, Mail, MapPin, Phone, Send } from 'lucide-vue-next';
const contactInfo = [
    {
        icon: Mail,
        bgColor: 'bg-pink-100',
        iconColor: 'text-pink-600',
        title: 'Email Address',
        detail: 'info@example.com',
        aos: 'fade-left',
        delay: '200'
    },
    {
        icon: Phone,
        bgColor: 'bg-yellow-100',
        iconColor: 'text-yellow-600',
        title: 'Phone Number',
        detail: '+1 (555) 123-4567',
        aos: 'fade-left',
        delay: '250'
    },
    {
        icon: MapPin,
        bgColor: 'bg-green-100',
        iconColor: 'text-green-600',
        title: 'Location',
        detail: '123 Main St, Anytown, USA',
        aos: 'fade-left',
        delay: '300'
    }
];
</script>