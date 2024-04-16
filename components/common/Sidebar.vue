<template>
        <div class="sidebar__wrapper">
            <div class="sidebar__logo">
                <img src="/testlogo.jpg" />
            </div>
            <div class="sidebar__navigation">
                <div class="sidebar__navigation__wrapper">
                    <div v-for="items in listNavigation" :key="items.id" class="sidebar__navigation__link" :class="{ active: route.path === items.link }" @click="navigateRouter(items.link)">
                        <div class="sidebar__navigation__link__wrapper" @click="items.sub ? handleNavSub() : '' ">
                             <span class="sidebar__navigation__link__icon">
                                <Icon :name="items.icon" color="black" />
                            </span>
                            <span class="sidebar__navigation__link__text">{{ items.name }}</span>
                            <span v-if="items.sub">
                                <Icon v-if="navSub" name="raphael:arrowup" />
                                <Icon v-else name="raphael:arrowdown" />
                            </span>
                        </div>
                        <div v-if="items.sub && navSub " class="sidebar__navigation__link__sub">
                            <div v-for="data in items.sub" :key="data.name" :class="{ active: route.path === data.link }" @click="navigateRouter(data.link)" class="sidebar__navigation__link__sub__field">
                                <span class="sidebar__navigation__link__sub__icon">
                                    <Icon :name="data.icon" color="black" />
                                </span>
                                <span class="sidebar__navigation__link__sub__text">{{ data.name }}</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
</template>


<script lang="ts">

export default defineNuxtComponent({

    setup(){

        const route = useRoute()
        const router = useRouter()
        const navSub = ref(false);

        const pageActive = ref(null)

        const listNavigation = ref([
            {
                id: 1,
                name: "Dashboard",
                icon: "material-symbols:dashboard-outline",
                link: "/admin/dashboard"
            },
            {
                id: 2,
                name: "Projects",
                icon: "ant-design:project-outlined",
                link: "",
                sub: [
                    {
                        name: "3D Models",
                        icon: "ant-design:project-outlined",
                        link: "/admin/project/3dmodels"
                    },
                    {
                        name: "Maps",
                        icon: "ant-design:project-outlined",
                        link: "/admin/project/maps"
                    },
                    {
                        name: "Videos",
                        icon: "ant-design:project-outlined",
                        link: "/admin/project/videos"
                    },
                ]
            },
            {
                id: 3,
                name: "Documentation",
                icon: "solar:document-broken",
                link: "/admin/document"
            },
            {
                id: 4,
                name: "User Management",
                icon: "mdi:user-outline",
                link: "/admin/user-management"
            },
        ])

        const handleNavSub = () => {
            navSub.value = !navSub.value
        }

        const navigateRouter = (index: string) => {
            router.push(index)
        }


        return {
            listNavigation,
            navigateRouter,
            navSub,
            handleNavSub,
            route
        }

    }
})

</script>


<style lang="scss"scoped>

.sidebar {

    &__wrapper {
        display: flex;
        flex-direction: column;
        gap: 20px;
        background: #ffffff;
        border: 1px solid #016DD3;
        height: 100vh;
    }

    &__logo {

        img {
            width: 100%;
        }
        
    }

    &__navigation {

        &__wrapper {
            display: flex;
            flex-direction: column;
            gap: 5px;

            @media (min-width: 768px) {
                gap: 0px;
            }

        }

        &__link {
            
            &__wrapper {
                display: flex;
                flex-direction: column;
                gap: 0px;
                cursor: pointer;
                padding: 7% 5%;
                text-align: center;

                @media (min-width: 768px) {
                    display: flex;
                    flex-direction: row;
                    gap: 10%;
                    align-items: center;
                    align-content: center;

                    &:hover {
                        background: #016DD3;
                        color: #ffffff;

                        svg {
                            color: #ffffff !important;
                        }

                    }

                }

            }

            svg {
                color: #016DD3 !important;
            }

            &__text {
                display: none;

                @media (min-width: 768px){
                    display: block;
                }
            }

            &__sub {

                display: flex;
                flex-direction: column;
                gap: 5px;
                cursor: pointer;

                &__field {
                    display: flex;
                    align-items: center;
                    gap: 10px;
                    padding: 4% 42%;

                    @media (min-width: 768px) {
                        padding: 5% 20%;
                    }
                    
                }

                &__icon {
                    font-size: 10px;
                }

                &__text {
                display: none;

                @media (min-width: 768px){
                    display: block;
                }
            }

            }

        }
        
    }

}

.active {
    background: #016DD3;
    color: #ffffff;

    svg {
        color: #ffffff !important;
    }
}

</style>