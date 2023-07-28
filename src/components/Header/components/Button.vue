<script>
export default {
}
</script>

<template>
    <button class="btn">
        <span class="btn__text">
            Gabung di IDN Times
        </span>
        <img class="btn__img" src="/images/profile.png" alt="Profile">
    </button>
</template>

<style lang='scss' scoped>
.btn {
    color: #e6001b;
    border: 1px solid #e6001b;
    font-family: "Poppins", sans-serif;
    font-weight: 600;
    border-radius: 4px 4px;
    padding: 9px 25px;
    background-color: transparent;
    font-size: 14px;
    cursor: pointer;

    &__img {
        display: none;
    }
}


@media (max-width: 768px) {
    .btn {
        padding: 0;
        border: none;
        height: 24px;

        &__text {
            display: none;
        }

        &__img {
            display: block;
        }
    }
}
</style>