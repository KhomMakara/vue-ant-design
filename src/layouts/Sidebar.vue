<template>
    <a-layout-sider width="200" style="background: #2a75bf">
        <div style="padding: 16px; text-align: center;">
            <img alt="Logo" src="@/assets/logo.svg" style="width: 40px; margin-bottom: 10px;" />
            <a-input-search placeholder="Search..." style="margin-bottom: 20px;" />
        </div>
        <a-menu
          v-model:openKeys="openKeys"
          v-model:selectedKeys="selectedKeys"
          style="background: #2a75bf; color: #fff; width: 200px"
          mode="inline"
          :theme="theme"
          :items="items"
        />
    </a-layout-sider>
</template>

<script setup>
import { h, ref } from 'vue';
import {
  MailOutlined,
  CalendarOutlined,
  AppstoreOutlined,
  SettingOutlined,
} from '@ant-design/icons-vue';
const theme = ref('dark');
const selectedKeys = ref(['1']);
const openKeys = ref(['sub1']);
const items = ref([
  {
    key: '1',
    icon: () => h(MailOutlined),
    label: 'Navigation One',
    title: 'Navigation One',
  },
  {
    key: '2',
    icon: () => h(CalendarOutlined),
    label: 'Navigation Two',
    title: 'Navigation Two',
  },
  {
    key: 'sub1',
    icon: () => h(AppstoreOutlined),
    label: 'Navigation Three',
    title: 'Navigation Three',
    children: [
      {
        key: '3',
        label: 'Option 3',
        title: 'Option 3',
      },
      {
        key: '4',
        label: 'Option 4',
        title: 'Option 4',
      },
      {
        key: 'sub1-2',
        label: 'Submenu',
        title: 'Submenu',
        children: [
          {
            key: '5',
            label: 'Option 5',
            title: 'Option 5',
          },
          {
            key: '6',
            label: 'Option 6',
            title: 'Option 6',
          },
        ],
      },
    ],
  },
  {
    key: 'sub2',
    icon: () => h(SettingOutlined),
    label: 'Navigation Four',
    title: 'Navigation Four',
    children: [
      {
        key: '7',
        label: 'Option 7',
        title: 'Option 7',
      },
      {
        key: '8',
        label: 'Option 8',
        title: 'Option 8',
      },
      {
        key: '9',
        label: 'Option 9',
        title: 'Option 9',
      },
      {
        key: '10',
        label: 'Option 10',
        title: 'Option 10',
      },
    ],
  },
]);
const changeTheme = checked => {
  theme.value = checked ? 'dark' : 'light';
};
</script>

<script>
import { Layout, Menu, Input, Switch } from 'ant-design-vue';
import { RouterLink } from 'vue-router';

export default {
    components: {
        'a-layout-sider': Layout.Sider,
        'a-menu': Menu,
        'a-sub-menu': Menu.SubMenu,
        'a-menu-item': Menu.Item,
        'a-input-search': Input.Search,
        'router-link': RouterLink,
        'a-switch': Switch
    }
}
</script>

<style scoped>
.a-menu-submenu-title .ant-menu-submenu-arrow {
    color: white;
    font-size: 20px;
}

.a-menu-item-active, .a-menu-item-selected {
    color: white !important;
}
</style>