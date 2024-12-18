<template>
  <div>
    <a-card>
      <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 20px;">
        <a-button type="primary" icon="user-add">Register</a-button>
      </div>
      <a-table :columns="columns" :data="data" :pagination="pagination" />
    </a-card>
  </div>
</template>

<script>
import ATable from '../shared/compoments/ATable.vue';
import { Card, Button } from 'ant-design-vue';

export default {
  components: {
    ATable,
    'a-card': Card,
    'a-button': Button,
  },
  data() {
    return {
      columns: [
        { title: 'Name', dataIndex: 'name', key: 'name' },
        { title: 'Age', dataIndex: 'age', key: 'age' },
        { title: 'Address', dataIndex: 'address', key: 'address' },
      ],
      data: [
        { key: '1', name: 'John Brown', age: 32, address: 'New York No. 1 Lake Park' },
        { key: '2', name: 'Jim Green', age: 42, address: 'London No. 1 Lake Park' },
        { key: '3', name: 'Joe Black', age: 32, address: 'Sidney No. 1 Lake Park' },
        { key: '4', name: 'Jim Red', age: 32, address: 'London No. 2 Lake Park' },
        { key: '5', name: 'Anna White', age: 28, address: 'Paris No. 1 Lake Park' },
        { key: '6', name: 'Tom Blue', age: 36, address: 'Berlin No. 1 Lake Park' },
        { key: '7', name: 'Lucy Brown', age: 29, address: 'Rome No. 1 Lake Park' },
        { key: '8', name: 'Chris Black', age: 31, address: 'Madrid No. 1 Lake Park' },
        { key: '9', name: 'Sara Green', age: 27, address: 'Dublin No. 1 Lake Park' },
        { key: '10', name: 'Mike Yellow', age: 34, address: 'Amsterdam No. 1 Lake Park' },
        { key: '11', name: 'Nina Purple', age: 30, address: 'Brussels No. 1 Lake Park' },
        { key: '12', name: 'Oscar Pink', age: 33, address: 'Vienna No. 1 Lake Park' },
        { key: '13', name: 'Eva Orange', age: 26, address: 'Prague No. 1 Lake Park' },
        { key: '14', name: 'Liam Gray', age: 35, address: 'Helsinki No. 1 Lake Park' },
        { key: '15', name: 'Sophia Cyan', age: 31, address: 'Lisbon No. 1 Lake Park' },
        { key: '16', name: 'Mason Red', age: 28, address: 'Warsaw No. 1 Lake Park' },
        { key: '17', name: 'Olivia Blue', age: 32, address: 'Oslo No. 1 Lake Park' },
        { key: '18', name: 'Lucas Green', age: 29, address: 'Stockholm No. 1 Lake Park' },
        { key: '19', name: 'Emma Brown', age: 33, address: 'Copenhagen No. 1 Lake Park' },
        { key: '20', name: 'Noah White', age: 30, address: 'Zurich No. 1 Lake Park' },
      ],
      pagination: {
        pageSize: 5,
        showSizeChanger: true,
        pageSizeOptions: ['5', '10', '20', '50'],
      },
    };
  },
};
</script>
