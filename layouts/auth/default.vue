<template>
    <div class="auth">
         <div class="auth__card">
                 <div class="auth__card__logo">
                    <div class="auth__card__logo__wrapper">
                        <div class="auth__card__logo__image">
                            <img src="/testlogo.jpg" alt="logo mandiri sekuritas priority" />
                        </div>
                    </div>
                 </div> 
                 <div class="auth__card__content">
                    <div class="auth__card__content__wrapper">
                        <div class="auth__card__content__title">
                           <h3>
                                {{title}}
                                <hr />
                            </h3>
                        </div>
                        <div class="auth__card__content__form">
                            <slot />
                        </div>
                    </div>
                 </div>
            </div>
    </div>
</template>

<script lang="ts">

export default defineNuxtComponent({

    props: {
        title: {
            required: true,
            type: String
        }
    },
    setup(){

    }

})

</script>

<style lang="scss" scoped>  

.auth{
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 0% 2%;

    &__card {
        padding: 5%;
        border-radius: 10px;
        display: grid;
        box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
        border: 1px solid #016DD3;
        grid-template-columns: 1fr;

        @media (min-width: 768px) {
            padding: 2%;
        }

    &__logo {

        display: none;

        @media (min-width: 768px) {
            display: block;
            align-self: center;
            margin-bottom: 20px;
            grid-row: 1 / span 2;

            &__wrapper {
                display: flex;
                justify-content: center;
                position: relative;
            }
        }

        &__image {
            max-width: 100%;
            height: auto;
            
            img {
                width: 500px;
            }

        }
    }

    &__content {
        display: flex;
        flex-direction: column;
        align-items: center;

        &__wrapper {
            display: flex;
            flex-direction: column;
            padding: 0px;
            margin-top: 0px;
            color: #003B78;

            h3 {
                margin: 50px 0px;
                text-align: center;
            }

        }

        &__form {
           width: 100%;
        }

        @media (min-width: 768px) {
            box-shadow: rgba(149, 157, 165, 0.5) 0px 8px 24px;
            border-radius: 25px;
        }

    }

    @media (min-width: 768px) {
        grid-template-columns: repeat(2, 1fr);
        gap: 20px;

        &__content {
            grid-column: 2;
            padding: 10% 2%;
            align-self: start;
        }
    }

    &__modal {

        &__wrapper {
            padding: 30px 0px;
            text-align: center;
        }

        &__description {
            font-size: 20px;
            font-weight: bold;
        }

        &__icon {
            font-size: 60px;
        }

    }
    }

}

</style>