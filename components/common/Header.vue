<template>
    <div class="header__wrapper">
        <div class="header__content">
            <div class="header__content__user">
                <span>
                    <Icon name="mdi:user-outline" />
                </span>
                <span> Admin </span>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.header {
    &__wrapper {
        display: flex;
        justify-content: flex-end; /* Menggeser konten ke kanan */
    }

    &__content {
        /* Tidak ada perubahan pada bagian ini */
        display: flex;
    }

    &__content__user {
        width: 90px;
        border: 1px solid #016DD3;
        border-radius: 10px;
        padding: 10px 19px;
        display: flex;
        justify-content: space-between;
    }
}
</style>
