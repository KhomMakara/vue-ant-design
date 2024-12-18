<template>
  <a-table :columns="enhancedColumns" :dataSource="data" :pagination="paginationConfig" />
</template>

<script>
import { Table } from 'ant-design-vue';

export default {
  components: {
    'a-table': Table,
  },
  props: {
    columns: {
      type: Array,
      required: true,
    },
    data: {
      type: Array,
      required: true,
    },
    pagination: {
      type: Object,
      default: () => ({
        pageSize: 10,
        showQuickJumper: true,
      }),
    },
  },
  computed: {
    enhancedColumns() {
      return this.columns.map(column => ({
        ...column,
        sorter: (a, b) => {
          if (typeof a[column.dataIndex] === 'number') {
            return a[column.dataIndex] - b[column.dataIndex];
          }
          return a[column.dataIndex].localeCompare(b[column.dataIndex]);
        },
      }));
    },
    paginationConfig() {
      return {
        ...this.pagination,
        showSizeChanger: true,
        pageSizeOptions: ['5', '10', '20', '50'],
      };
    },
  },
};
</script>

<style scoped>
.a-table {
  width: 100%;
}
</style>
