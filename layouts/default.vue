<template>
    <div class="main">
        <div class="wrapper">
            <div class="sidebar">
                <CommonSidebar />
            </div>
            <div class="content">
                <div class="content__wrapper">
                    <div class="content__header">
                        <CommonHeader />
                    </div>
                    <div class="content__main">
                        <slot />
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>

.main {

    .wrapper {
        display: grid;
        grid-template-columns: 15% 85%;
        max-width: 100%;
    }
    
    .content {

        &__wrapper {
            max-width: 100%;
            width: 100%;
            display: flex;
            flex-direction: column;
            gap: 30px;
            padding: 10px;

            @media (min-width: 768px) {
                padding: 5% 5%;
            }

        }

        &__main {
            max-width: 100%;
            width: 100%;
        }

    }

}

</style>