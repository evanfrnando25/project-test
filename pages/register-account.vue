<template>
    <NuxtLayout name="auth-default" title="Register">
         <div class="auth__wrapper">
            <div class="auth__field">
                <span>Name</span>
                <input type="text" placeholder="name" />
            </div>
            <div class="auth__field">
                <span>Email</span>
                <input type="text" placeholder="email" />
            </div>
             <div class="auth__field">
                <span>Password</span>
                <input type="password" placeholder="password" />
            </div>
            <div class="auth__forgot-password">
                <span @click="loginPage">Did you have an account ?</span>
            </div>
             <div class="auth__action">
                <button>Register</button>
            </div>
        </div>
    </NuxtLayout>
</template>



<script lang="ts" setup>

definePageMeta({
  layout: false,
});

const router = useRouter()

const loginPage = () => {
    router.push("/login")
}

</script>


<style lang="scss" scoped>

.auth {

    &__wrapper {
        display: flex;
        flex-direction: column; 
        gap: 20px;
        width: 100%;

        @media (min-width: 768px) {
            width: 200px;
        }

    }

    &__field {
        display: flex;
        flex-direction: column;
        gap: 10px;

        input {
            background: transparent;
            border: 1px solid ;
            padding: 5px;
            border-radius: 5px;
        }

    }

    &__forgot-password {
        text-align: end;
        font-size: 10px;
        cursor: pointer;
    }

    &__action {
        
        button {
             cursor: pointer;
            width: 100%;
             background: #003B78;
                    color: #ffffff;
                    border: none;
                    border-radius: 5px;
                    padding: 5px;
                    font-size: 10px;
                    letter-spacing: 2px;
        }

    }


}

</style>