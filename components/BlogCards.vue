<script setup>
const {data, pending, error} = useLazyFetch('https://dummyjson.com/posts?limit=10')

</script>

<template>
    <div>
        <div class="py-[100px] bg-gray-900">
            <h1 class="text-white text-6xl text-center mb-14">Our Blogs</h1>
            <div class="flex flex-wrap justify-center gap-8 px-4 md:px-[80px]">
                <div v-for="post in data.posts" class="">
                    <Card :id="post.id" :title='post.title' :description="post.body"
                        imageSrc="https://img.freepik.com/free-photo/rear-view-programmer-working-all-night-long_1098-18697.jpg?size=626&ext=jpg&ga=GA1.1.1224184972.1714608000&semt=sph" />
                </div>

            </div>
        </div>
    </div>
</template>