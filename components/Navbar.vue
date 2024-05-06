<template>
    <nav class="w-full text-white text-lg p-6 bg-gray-900 relative">
        <div class="flex items-center justify-between">

            <!-- Header logo -->
            <div>
                <NuxtLink to="/" class="text-3xl">Blogify</NuxtLink>
            </div>

            <!-- Mobile toggle -->
            <div class="md:hidden">
                <button @click="drawer">
                    <svg class="h-8 w-8 fill-current text-white" fill="none" stroke-linecap="round"
                        stroke-linejoin="round" stroke-width="2" viewBox="0 0 24 24" stroke="currentColor">
                        <path d="M4 6h16M4 12h16M4 18h16"></path>
                    </svg>
                </button>
            </div>

            <!-- Navbar -->
            <div class="hidden md:block">
                <ul class="flex space-x-8  font-sans">
                    <li><NuxtLink to="/" class="">Home</NuxtLink></li>
                    <li><NuxtLink to="/about" class="">About</NuxtLink></li>
                    <li><NuxtLink to="/blogs" class="">All Blogs</NuxtLink></li>
                    <li><NuxtLink to="/contact" class="">Contact</NuxtLink></li>
                    <li><NuxtLink to="/signup"
                            class="cta bg-blue-500 hover:bg-blue-600 text-base px-6 py-3 rounded text-white font-semibold">Sign
                            Up</NuxtLink></li>
                </ul>
            </div>

            <!-- Dark Background Transition -->
            <transition enter-class="opacity-0" enter-active-class="ease-out transition-medium"
                enter-to-class="opacity-100" leave-class="opacity-100" leave-active-class="ease-out transition-medium"
                leave-to-class="opacity-0">
                <div @keydown.esc="isOpen = false" v-show="isOpen" class="z-10 fixed inset-0 transition-opacity">
                    <div @click="isOpen = false" class="absolute inset-0 bg-black opacity-50" tabindex="0"></div>
                </div>
            </transition>

            <!-- Drawer Menu -->
            <aside
                class="p-5 transform top-0 left-0 w-64 bg-white fixed h-full overflow-auto ease-in-out transition-all duration-300 z-30"
                :class="isOpen ? 'translate-x-0' : '-translate-x-full'">

                <div class="close">
                    <button class="absolute text-gray-900 top-0 right-0 mt-4 mr-4" @click=" isOpen = false">
                        <svg class="w-6 h-6" fill="none" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                            viewBox="0 0 24 24" stroke="currentColor">
                            <path d="M6 18L18 6M6 6l12 12"></path>
                        </svg>
                    </button>
                </div>

                <span @click="isOpen = false" class="flex w-full items-center p-4 pl-0 border-b">
                    <NuxtLink to="/" class="text-gray-900 text-2xl">Blogify</NuxtLink>
                </span>

                <ul class="divide-y font-sans text-gray-900">
                    <li><NuxtLink to="/" @click="isOpen = false" class="my-4 inline-block">Home</NuxtLink></li>
                    <li><NuxtLink to="/about" @click="isOpen = false" class="my-4 inline-block">About</NuxtLink></li>
                    <li><NuxtLink to="/blogs" @click="isOpen = false" class="my-4 inline-block">All blogs</NuxtLink></li>
                    <li><NuxtLink to="/contact" @click="isOpen = false" class="my-4 inline-block">Contact</NuxtLink></li>
                    <li><NuxtLink to="/signup" @click="isOpen = false"
                            class="my-8 w-full text-center font-semibold text-base cta inline-block bg-gray-700 hover:bg-gray-900 px-3 py-2 rounded text-white">Sign
                            Up</NuxtLink></li>
                </ul>


            </aside>

        </div>
    </nav>
</template>

<script>
export default {
    data() {
        return {
            isOpen: false
        };
    },
    methods: {
        drawer() {
            this.isOpen = !this.isOpen;
        }
    },
    watch: {
        isOpen: {
            immediate: true,
            handler(isOpen) {
                if (process.client) {
                    if (isOpen) document.body.style.setProperty("overflow", "hidden");
                    else document.body.style.removeProperty("overflow");
                }
            }
        }
    },
    mounted() {
        document.addEventListener("keydown", e => {
            if (e.keyCode == 27 && this.isOpen) this.isOpen = false;
        });
    }
};
</script>
