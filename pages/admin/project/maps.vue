<template>
    <div class="project">
        <div class="project__wrapper">
            <div class="project__header">
                <h5>Project Maps</h5>
            </div>
            <div class="project__content">
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
    .project {
        &__wrapper {
            display: flex;
            flex-direction: column;
            gap: 50px;
        }

        &__header {
            h5 {
                font-weight: 600;
            }
        }
    }
</style>
