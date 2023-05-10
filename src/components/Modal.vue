<template>
    <div class="backdrop">
        <div class="modal" :class="{ sale: theme === 'sale' }">
            <h1>{{ header }}</h1>
            <p>{{ text }}</p>
        </div>
    </div>
</template>

<script>
export default {
    props: ["header", "text", "theme"],
};
</script>

<style scooped lang="scss">
.backdrop {
    top: 0;
    position: fixed;
    background: rgba(0, 0, 0, 0.5);
    width: 100%;
    height: 100%;

    .modal {
        width: 500px;
        padding: 20px;
        margin: 100px auto;
        background: #ffffff;
        border-radius: 10px;

        h1 {
            color: rgb(112, 13, 143);
            border: none;
            padding: 0;
            font-weight: 700;
            text-align: center;
            margin: 10px;
        }

        p {
            text-align: center;
        }
    }

    .modal.sale {
        background: #ca3636;
        color: #fff;

        h1 {
            color: #fff;
        }
    }
}
</style>
