<template>
  <div class="table">
    <q-table flat bordered :rows="data" :columns="columns" row-key="pageIndex">
      <template v-slot:top>
        <span class="table-search">
          <input type="text" />
        </span>
        <q-space />
        <span class="table-export">
          <button>Export Excel</button>
        </span>
      </template>
      <template v-slot:header="props">
        <q-tr :props="props">
          <q-th>No.</q-th>
          <q-th v-for="col in props.cols" :key="col.name" :props="props">
            {{ col.label }}
          </q-th>
          <q-th v-if="action">Action</q-th>
        </q-tr>
      </template>
      <template v-slot:body="props">
        <q-tr :props="props">
          <q-td auto-width>
            {{ props.pageIndex + 1 }}
          </q-td>
          <q-td v-for="col in props.cols" :key="col.name" :props="props">
            {{ col.value }}
          </q-td>
          <q-td class="text-center" v-if="action">
            <div class="action-section">
              <button
                v-for="items in action"
                :key="items.id"
                :class="'button-' + items.label.toLowerCase()"
                @click="
                  items.params === true
                    ? $emit(
                        `handle${items.label}`,
                        props.row[items.routeParams]
                      )
                    : $emit(`handle${items.label}`)
                "
              >
                {{ items.label }}
              </button>
            </div>
          </q-td>
        </q-tr>
      </template>
    </q-table>
  </div>
</template>

<script lang="ts">

export default defineNuxtComponent({
  props: {
    columns: {
      required: false,
      type: Array || null,
    },
    data: {
      required: false,
      type: Array || null,
    },
    action: {
      required: false,
      type: Array || null,
    },
  },
  setup(props: any, { emit }: any) {
    return {};
  },
});

</script>

<style lang="scss" scoped>

.table-search {
  input {
    border-radius: 10px;
    border: 1px solid #ddd;
    height: 47px;
    padding: 2% 4%;
    width: 100%;
    outline: none;

    @media (min-width: 768px) {
      padding: 5% 3% 5% 5%;
    }
  }
}

.table-export {
  button {
    border-radius: 5px;
    background: $primary-100;
    padding: 10% 10px;
    color: $basic;
    border: none;
    cursor: pointer;
  }
}

.action-section {
  justify-content: center;
  display: flex;
  gap: 5%;
  position: relative;

  .button-detail {
    background: $primary-100;
    color: $basic;
    padding: 15% 20%;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }

  .button-submerchant {
    background: $primary-100;
    color: $basic;
    padding: 8% 10%;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }

  .button-process {
    background: $primary-100;
    color: $basic;
    padding: 8% 10%;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }
}
</style>