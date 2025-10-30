<template>
    <section id="service" class="relative overflow-hidden bg-linear-to-br from-gray-50 to-green-50 
        py-12 px-4 sm:py-16 md:py-20 md:px-12 lg:px-20">
        <div class="max-w-7xl mx-auto">
            <div class="flex flex-col lg:flex-row items-center justify-center text-center mb-6"
                data-aos="fade-down">
                <div class="flex-1 max-w-2xl mx-auto space-y-6 mb-10 lg:mb-0">
                    <div>
                        <h2 class="text-4xl sm:text-5xl text-gray-900">
                            Our 
                            <span class="font-bold text-black">Services</span> 
                            <span class="text-green-500">.</span>
                        </h2>
                        <div class="flex gap-3 mt-4 justify-center">
                            <Circle class="text-pink-500 w-5 h-5" />
                            <Circle class="text-yellow-500 w-5 h-5" />
                            <Circle class="text-green-500 w-5 h-5" />
                        </div>
                    </div>
                </div>
            </div>

            <div class="flex flex-wrap gap-3 sm:gap-4 mb-8 sm:mb-12 justify-center"
                data-aos="fade-up" data-aos-delay="100">
                <button v-for="service in services" :key="service.id"
                    @click="activeService = service.id"
                    :class="`px-4 py-2 sm:px-6 sm:py-3 rounded-full font-medium flex items-center gap-2
                        transition-all text-sm sm:text-base 
                        ${activeService === service.id 
                        ? `${service.color} text-white shadow-lg` 
                        : 'bg-white text-gray-700 shadow-md hover:shadow-lg'}`"
                    :data-aos="'fade-up'" 
                    :data-aos-delay="service.id * 100">
                    <component :is="service.icon" class="w-5 h-5 sm:w-6 sm:h-6" />
                    {{ service.title }}
                </button>
            </div>

            <div class="bg-white rounded-2xl md:rounded-3xl shadow-lg p-6 sm:p-8 mb-12 sm:mb-16 border border-gray-100"
                data-aos="fade-up" data-aos-delay="200">
                <div v-for="service in services.filter(s => s.id === activeService)" 
                    :key="service.id"
                    class="flex flex-col lg:flex-row gap-6 md:gap-10">
                    <div class="flex-1">
                        <div class="flex items-center gap-3 sm:gap-4 mb-4 sm:mb-6"
                            data-aos="fade-right" data-aos-delay="300">
                            <div :class="`w-12 h-12 sm:w-16 sm:h-16 rounded-lg sm:rounded-xl flex items-center justify-center
                                ${service.color}`">
                                <div :class="service.iconColor">
                                    <component :is="service.icon" class="w-5 h-5 sm:w-6 sm:h-6"/>
                                </div>
                            </div>
                            <h3 class="text-2xl sm:text-3xl font-bold text-gray-800">{{ service.title }}</h3>
                        </div>
                        <p class="text-base sm:text-lg text-gray-700 mb-4 sm:mb-6 leading-relaxed"
                            data-aos="fade-right" data-aos-delay="350">
                            {{ service.description }}
                        </p>
                        <div class="grid grid-cols-1 sm:grid-cols-2 gap-3 sm:gap-4 mb-6 sm:mb-8"
                            data-aos="fade-left" data-aos-delay="400">
                            <div v-for="(feature, index) in service.features" 
                                :key="index" 
                                class="flex items-center gap-2" data-aos="fade-up" :data-aos-delay="500 + index * 100">
                                <CheckCircle class="w-4 h-4 sm:w-5 sm:h-5 text-green-500 mr-2 shrink-0" />
                                <span class="text-gray-700 text-sm sm:text-base">{{ feature }}</span>
                            </div>
                        </div>
                        <div class="flex justify-center lg:justify-start" data-aos="fade-up" data-aos-delay="600">
                            <button
                                :class="`${service.buttonColor} px-6 py-3 sm:px-8 sm:py-4 shadow-md rounded-full text-white font-medium 
                                    hover:shadow-lg transition-all flex items-center gap-2 text-sm sm:text-base`">
                                Get This Service
                                <ArrowRight class="w-4 h-4 sm:w-5 sm:h-5 inline-block ml-1" />
                            </button>
                        </div>
                    </div>

                    <div class="flex-1 mt-6 lg:mt-0" data-aos="zoom-in" data-aos-delay="500">
                        <div class="w-full h-60 sm:h-72 md:h-80 overflow-hidden shadow-lg rounded-xl md:rounded-2xl">
                            <img :src="service.image" :alt="service.title"
                                class="object-cover w-full h-full transform hover:scale-105 transition-transform duration-700">
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <div class="hidden md:block absolute border-2 border-pink-500 bottom-20 left-10 w-16 h-16 sm:w-20 sm:h-20 md:w-24 md:h-24
            rounded-full opacity-50" data-aos="zoom-in" data-aos-delay="700"></div>
        <div class="hidden md:block absolute border-2 border-green-500 top-40 right-10 w-20 h-20 sm:w-24 sm:h-24 md:w-32 md:h-32
            rounded-full opacity-50" data-aos="zoom-in" data-aos-delay="800"></div>
    </section>
</template>
<script setup>
import { ref } from 'vue';
import { ArrowRight, Brush, Camera, CheckCircle, Circle, Code } from 'lucide-vue-next';

const activeService = ref(1);
const services = [
    {
        id: 1,
        icon: Brush,
        title: 'UI/UX Design',
        description: 'Creating user-friendly and visually appealing designs for web and mobile applications.',
        features: [
            'User Research and Analysis',
            'Wireframing and Prototyping',
            'Visual Design and Branding',
            'Login Design and Branding',
            'Mobile App Design',
        ],
        color: 'bg-pink-400',
        buttonColor: 'bg-pink-400 hover:bg-pink-500',
        iconColor: 'text-pink-100',
        image: '/service1.jpg'
    },
    {
        id: 2,
        icon: Code,
        title: 'Web Development',
        description: 'Building responsive and high-performance websites and applications.',
        features: [
            'Front-end Development',
            'Back-end Development',
            'API Development',
            'Mobile Responsive Design',
            'E-commerce Solutions',
        ],
        color: 'bg-yellow-500',
        buttonColor: 'bg-yellow-500 hover:bg-yellow-600',
        iconColor: 'text-yellow-200',
        image: '/service2.jpg'
    },
    {
        id: 3,
        icon: Camera,
        title: 'Photography',
        description: 'Capturing stunning images and videos for various purposes.',
        features: [
            'Event Photography',
            'Product Photography',
            'Wedding Photography',
            'Portrait Photography',
            'Video Photography',
        ],
        color: 'bg-green-500',
        buttonColor: 'bg-green-500 hover:bg-green-600',
        iconColor: 'text-green-200',
        image: '/service3.jpg'
    }
];
</script>