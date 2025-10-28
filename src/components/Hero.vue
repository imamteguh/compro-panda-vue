<template>
    <section class="w-full flex items-center justify-center bg-gray-50">
        <div class="max-w-7xl overflow-hidden bg-gray-50 py-12 px-4 sm:px-6 md:px-8 lg:px-20 flex flex-col lg:flex-row items-center justify-between">
            <div class="flex-1 w-full max-w-xl space-y-6 relative z-20">
                <h2 class="text-4xl sm:text-5xl text-gray-900 text-center lg:text-left mt-8" data-aos="fade-right">
                    professionals 
                    <span class="font-bold text-black block lg:inline">Service</span> 
                    <span class="text-green-500">.</span>
                </h2>
                <div class="flex gap-3 mt-4 justify-center lg:justify-start" data-aos="fade-right" data-aos-delay="100">
                    <Circle class="text-pink-500 w-5 h-5" />
                    <Circle class="text-yellow-500 w-5 h-5" />
                    <Circle class="text-green-500 w-5 h-5" />
                </div>
                <div class="flex flex-col lg:grid lg:grid-cols-2 gap-6 lg:gap-40 items-center lg:items-start">
                    <div class="bg-white w-72 rounded-3xl p-6 border border-gray-100 shadow-xl lg:shadow-2xl transition"
                        data-aos="zoom-in" data-aos-delay="200">
                        <div class="ml-4 w-10 h-10 flex items-center justify-center rounded-lg bg-pink-100 mb-4">
                            <span class="text-pink-500 text-xl">
                                <Heart class="text-pink-600 w-6 h-6" />
                            </span>
                        </div>
                        <h3 class="ml-4 text-lg font-semibold text-gray-800">
                            Service Subtitle One
                        </h3>
                        <p class="ml-4 text-gray-500 text-sm mt-2">
                            Lorem ipsum dolor sit amet consectetur, adipisicing elit.
                        </p>
                    </div>
    
                    <div class="bg-white w-72 rounded-3xl p-6 border border-gray-100 shadow-xl lg:shadow-2xl transition relative z-30"
                        data-aos="zoom-in" data-aos-delay="300">
                        <div class="ml-4 w-10 h-10 flex items-center justify-center rounded-lg bg-yellow-100 mb-4">
                            <span class="text-yellow-500 text-xl">
                                <Award class="text-yellow-600 w-6 h-6" />
                            </span>
                        </div>
                        <h3 class="ml-4 text-lg font-semibold text-gray-800">
                            Service Subtitle Two
                        </h3>
                        <p class="ml-4 text-gray-500 text-sm mt-2">
                            Lorem ipsum dolor sit amet consectetur, adipisicing elit.
                        </p>
                    </div>
                </div>
            </div>
    
            <div class="flex-1 mt-12 lg:mt-8 lg:ml-24 relative w-full flex justify-center" 
                data-aos="fade-left" data-aos-delay="400">
                <div class="w-64 h-64 sm:w-80 sm:h-80 md:w-96 md:h-96 lg:w-[550px] lg:h-[460px] overflow-hidden
                    border-8 border-white shadow-lg lg:shadow-lg rounded-[60%_40%_30%_60%/60%_30%_70%_30%]
                    relative z-10">
                    <img src="/panda.jpg" alt="hero" class="object-cover w-full">
                </div>
            </div>
        </div>
    </section>
</template>
<script setup>
import { Award, Circle, Heart } from 'lucide-vue-next';

</script>