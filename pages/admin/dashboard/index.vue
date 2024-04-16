<template>
    <div class="dashboard">
        <div class="dashboard__higlight">
            <div v-for="items in listHiglight" :key="items.id" class="dashboard__higlight__card">
                <CommonCard>
                    <div class="card__content__wrapper">
                        <div class="card__content__header">
                            {{ items.name }}
                        </div>
                        <div class="card__content__text">
                            {{ items.total }}
                        </div>
                        <div class="card__content__footer">Updated {{ items.update }}</div>
                    </div>
                </CommonCard>
            </div>
        </div>
        <div class="dashboard__content">
            <div class="dashboard__content__wrapper">
                <CommonTable
                    :data="data"
                    :columns="columns"
                    :action="action"
                    @handleDetail="handleDetail"
                />
            </div>
        </div>
    </div>
</template>

<script lang="ts">
    export default defineComponent({
        setup() {
            const listHiglight = ref([
                {
                    id: 1,
                    name: 'Total All Project Actived ',
                    total: 20,
                    update: '2 Days Ago',
                },
                {
                    id: 2,
                    name: 'Total Project 3D Models',
                    total: 10,
                    update: '2 Days Ago',
                },
                {
                    id: 3,
                    name: 'Total Project Maps',
                    total: 5,
                    update: '2 Days Ago',
                },
                {
                    id: 4,
                    name: 'Total Project Videos',
                    total: 5,
                    update: '2 Days Ago',
                },
            ])

            const columns = ref([
                { name: 'merchantID', label: 'Accunt ID', field: 'merchantID', align: 'center' },
                { name: 'merchantName', label: 'Name', field: 'merchantName', align: 'center' },
                { name: 'revenue', label: 'Category', field: 'revenue', align: 'center' },
                { name: 'status', label: 'Created At', field: 'status', align: 'center' },
                { name: 'status', label: 'Created At', field: 'status', align: 'center' },
            ])

            const action = ref([
                {
                    id: '0',
                    label: 'Detail',
                    params: true,
                    routeParams: 'merchantID',
                },
            ])

            const data = [
                {
                    merchantID: 312312312,
                    merchantName: 'STARBUCKS',
                    revenue: 500.0,
                    status: 'Active',
                    durationDeactive: '30 Days',
                    lastUpdated: '13-07-2023, 23:59',
                },
                {
                    merchantID: 312312312,
                    merchantName: 'STARBUCKS',
                    revenue: 500.0,
                    status: 'Active',
                    durationDeactive: '30 Days',
                    lastUpdated: '13-07-2023, 23:59',
                },
            ]

            return {
                data,
                action,
                columns,
                listHiglight,
            }
        },
    })
</script>

<style lang="scss" scoped>
    .dashboard {
        display: grid;
        grid-template-columns: repeat(1, 1fr);
        gap: 50px;
        width: 100%;

        &__higlight {
            display: grid;
            grid-template-columns: repeat(1, 1fr);
            gap: 10px;

            @media (min-width: 400px) {
                grid-template-columns: repeat(2, 1fr);
            }

            @media (min-width: 768px) {
                grid-template-columns: repeat(3, 1fr);
            }
        }

        &__content {
            width: 100%;
            overflow: hidden;
        }
    }

    .card__content {
        &__wrapper {
            display: flex;
            flex-direction: column;
            gap: 15px;
            padding: 2% 3%;
            height: 100%;
        }

        &__header,
        &__text,
        &__footer {
            height: 33.33%; // Memberikan tinggi yang sama untuk setiap bagian
        }

        &__header {
            font-size: 15px;
            font-weight: bold;
        }

        &__text {
            font-size: 20px;
            font-weight: bold;
        }

        &__footer {
            font-size: 8px;
            font-weight: 300;
            letter-spacing: 1px;
        }
    }
</style>
