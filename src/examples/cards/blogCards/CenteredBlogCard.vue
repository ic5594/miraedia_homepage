<script setup>
defineProps({
    image: {
        type: String,
        required: true,
    },
    title: {
        type: String,
        required: true,
    },
    description: {
        type: String,
        required: true,
    },
    action: {
        type: Object,
        color: String,
        route: String,
        label: String,
        default: () => ({
            color: "bg-gradient-success",
            label: "Send an email",
        }),
    },
});
</script>
<template>
    <div class="card">
        <div class="card-header p-0 position-relative mx-3 z-index-2">
            <a :href="action.route" class="d-block blur-shadow-image" style="display: flex !important; justify-content: center;">
                <img :src="image" :alt="title" class="img-fluid border-radius-lg" />
            </a>
        </div>
        <div class="card-body text-center">
            <h5 class="font-weight-normal">
                <a href="javascript:;">{{ title }}</a>
            </h5>
            <p class="mb-0">
                {{ description }}
            </p>
            <a href="mailto: djlee@miraedia.co.kr" type="button" class="btn btn-sm mb-0 mt-3" :class="action.color" @click="sendEmail">
                {{ action.label }}
            </a>
        </div>
    </div>
</template>
