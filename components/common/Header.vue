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
            align-items: center;
            align-content: center;
        }

        &__content__user {
            width: 90px;
            border: 1px solid #016dd3;
            border-radius: 10px;
            padding: 10px 19px;
            display: flex;
            gap: 10%;
            justify-content: space-between;

            span {
                align-items: center;
                align-content: center;
                align-self: center;
            }
        }
    }
</style>
