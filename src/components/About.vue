<template>
    <section id="about" class="relative overflow-hidden bg-linear-to-br from-gray-50 to-green-50 flex items-center justify-center">
        <div class="max-w-7xl py-12 px-4 sm:py-16 md:py-20 md:px-12 lg:px-20 flex flex-col lg:flex-row items-center justify-between">
            <div class="flex-1 w-full lg:mr-8 xl:mr-12 relative order-2 lg:order-1 mt-10 lg:mt-0">
                <div class="w-full max-w-md mx-auto lg:max-w-lg xl:max-w-xl h-[300px] sm:h-[350px]
                    md:h-[400px] lg:h-[450px] xl:h-[500px] overflow-hidden shadow-lg md:shadow-xl
                    rounded-[40%_60%_70%_30%/40%_50%_60%_60%] relative z-10 border-6 md:border-8 border-white -rotate-2 hover:rotate-0
                    transition-transform duration-700" data-aos="fade-right" data-aos-delay="200">
                    <img src="/about-panda.jpg" alt="about" class="object-cover w-full h-full transform hover:scale-110 transition-transform duration-700">
                </div>
    
                <div class="hidden md:block absolute border-2 border-pink-500 -bottom-4 -right-4 
                    w-16 h-16 md:w-20 md:h-20 lg:w-24 lg:h-24 rounded-full z-0" data-aos="zoom-in" data-aos-delay="500"></div>
                <div class="hidden md:block absolute border-2 border-green-500 -top-4 -left-4 
                    w-16 h-16 md:w-18 md:h-18 rounded-full z-0" data-aos="zoom-in" data-aos-delay="600"></div>
            </div>
    
            <div class="flex-1 w-full max-w-2xl mx-auto lg:mx-0 space-y-6 md:space-y-8 relative 
                z-20 order-1 lg:order-2">
                <div class="mb-6 md:mb-8" data-aos="fade-left">
                    <h2 class="text-4xl sm:text-5xl text-gray-900 text-center lg:text-left mt-8" data-aos="fade-right">
                        Agency 
                        <span class="font-bold text-black block lg:inline">Overview</span> 
                        <span class="text-green-500">.</span>
                    </h2>
                    <div class="flex gap-3 mt-4 justify-center lg:justify-start" data-aos="fade-right" data-aos-delay="100">
                        <Circle class="text-pink-500 w-5 h-5" />
                        <Circle class="text-yellow-500 w-5 h-5" />
                        <Circle class="text-green-500 w-5 h-5" />
                    </div>
                </div>
                <p class="text-base sm:text-lg text-gray-700 leading-relaxed text-center lg:text-left" data-aos="fade-up" data-aos-delay="200">
                    Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ab, voluptas recusandae fuga libero harum quis qui, 
                    repudiandae ipsum, ratione neque dolorem hic! Enim modi neque aperiam libero repellendus esse autem.
                </p>

                <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 md:gap-6 mt-8 md:mt-10" data-aos="fade-left" data-aos-delay="200">
                    <div v-for="(item, index) in featureItems" :key="index"
                        class="bg-white p-4 md:p-6 rounded-xl md:rounded-2xl border border-gray-100 shadow-md md:shadow-lg transition-all
                        hover:shadow-xl">
                        <div :class="`w-10 h-10 md:w-12 md:h-12 flex items-center justify-center rounded-lg ${item.bgColor} mb-3 md:mb-4`">
                            <component :is="item.icon" :class="`${item.iconColor} w-5 h-5 md:w-6 md:h-6`" />
                        </div>
                        <h3 class="text-base text-gray-800 md:text-lg font-semibold mb-2">{{ item.title }}</h3>
                        <p class="text-gray-600 text-xs md:text-sm">{{ item.description }}</p>
                    </div>
                </div>

                <div class="flex justify-center lg:justify-start mt-8 lg:mt-10" data-aos="fade-up" data-aos-delay="200">
                    <button class="px-6 py-3 md:px-8 md:py-4 bg-pink-500 text-white rounded-full font-medium hover:bg-pink-600 
                        transition-all shadow-md hover:shadow-lg flex items-center gap-2 text-sm md:text-base">
                        Learn More About Us
                        <ArrowRight class="w-4 h-4 md:w-5 md:h-5" />
                    </button>
                </div>
            </div>
        </div>
    </section>
</template>
<script setup>
import { ArrowRight, Circle, Target, Users } from 'lucide-vue-next';

const featureItems = [
    {
        icon: Users,
        bgColor: 'bg-pink-100',
        iconColor: 'text-pink-600',
        title: 'Expert Team',
        description: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit'
    },
    {
        icon: Target,
        bgColor: 'bg-yellow-100',
        iconColor: 'text-yellow-600',
        title: 'Our Mission',
        description: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit'
    }
]
</script>