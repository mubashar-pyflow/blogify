<script setup>
const route = useRoute();
const {data:post, pending, error} = useLazyFetch(`https://dummyjson.com/posts/${route.params.id}`);


</script>


<template>
    <div>
        <BlogPost :title="post.title" :description="post.body"  />
    </div>
</template>