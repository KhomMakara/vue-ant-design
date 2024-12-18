<template>
    <a-layout-header style="background: #2a75bf; display: flex; justify-content: space-between; align-items: center;">
        <div style="color: #fff; font-size: 20px;">Dashboard Header</div>
        <div style="display: flex; align-items: center;">
            <a-dropdown>
                <template #overlay>
                    <a-menu style="width: 200px;">
                        <a-menu-item key="1" style="padding: 10px 20px;">Notification 1</a-menu-item>
                        <a-menu-item key="2" style="padding: 10px 20px;">Notification 2</a-menu-item>
                    </a-menu>
                </template>
                <a href="#" class="ant-dropdown-link" @click="e => e.preventDefault()">
                    <BellOutlined style="font-size: 20px; color: #fff; margin-right: 16px;" />
                </a>
            </a-dropdown>
            <a-dropdown>
                <template #overlay>
                    <a-menu style="width: 200px;">
                        <a-menu-item key="1" style="padding: 10px 20px;">Logout</a-menu-item>
                        <a-menu-item key="2" style="padding: 10px 20px;">More</a-menu-item>
                    </a-menu>
                </template>
                <a href="#" class="ant-dropdown-link" @click="e => e.preventDefault()">
                    <UserOutlined style="font-size: 20px; color: #fff;" />
                </a>
            </a-dropdown>
        </div>
    </a-layout-header>
</template>

<script>
import { Layout, Dropdown, Menu } from 'ant-design-vue';
import { BellOutlined, UserOutlined } from '@ant-design/icons-vue';

export default {
    components: {
        'a-layout-header': Layout.Header,
        'a-dropdown': Dropdown,
        'a-menu': Menu,
        'a-menu-item': Menu.Item,
        BellOutlined,
        UserOutlined
    }
}
</script>