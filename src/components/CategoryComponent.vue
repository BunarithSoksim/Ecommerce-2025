<template>
    <div>
        <div :class="['w-34 h-44 relative rounded-lg flex flex-col items-center']" :style="{backgroundColor: bgColor}">
            <img :src="image" :alt="title" class="w-30 h-30"/>
            <div class="flex flex-col justify-center items-center">
                <p class="text-base">{{ title }}</p>
                <p class="text-xs">{{ itemCount }} items</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "CategoryComponent",
    props: {
        title: {
            type: String,
            required: true
        },
        itemCount: {
            type: Number,
            required: true
        },
        image: {
            type: String,
            required: true
        },
        bgColor: {
            type: String,
            required: true
        },
    },
};
</script>