<template>
    <div class="backdrop" @click="closeModal">
        <!-- Class is sale if theme prop = 'sale' -->
        <div class="modal" :class="{ sale: theme === 'sale' }">
            <h1>Modal Content</h1>
            <p>{{ header }}</p>
            <p>{{ header2 }}</p>
        </div>
    </div>
</template>

<script>
export default {
    // Taking in props
    props: ['header', 'header2', 'theme'],
    methods: {
        closeModal() {
            // Custom event - listened to from parent component
            this.$emit('close')
        }
    }
}
</script>

// Scoped - styles only apply to this component
<style scoped>
    .modal {
        width: 400px;
        padding: 200px;
        margin: 100px auto;
        background: white;
        border-radius: 10px;
    }
    .backdrop {
        top: 0;
        left: 0;
        position: fixed;
        background: rgba(0, 0, 0, 0.5);
        width: 100%;
        height: 100%;
    }
    h1 {
        color: red;
    }
    .sale {
        background: green;
        color: white;
    }
</style>