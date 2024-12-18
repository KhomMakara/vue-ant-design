<template>
    <a-layout style="min-height: 100vh">
        <Sidebar />
        <a-layout>
            <Header />
            <a-layout-content style="margin: 24px 16px 0">
                <div style="padding: 24px; background: #fff; min-height: 360px">
                    Content goes here
                </div>
            </a-layout-content>
            <a-layout-footer style="text-align: center">
                Ant Design 2023 Created by Ant UED
            </a-layout-footer>
        </a-layout>
    </a-layout>
</template>

<script>
import { Layout } from 'ant-design-vue';
import Sidebar from './Sidebar.vue';
import Header from './Header.vue';

export default {
    components: {
        'a-layout': Layout,
        Sidebar,
        Header
    }
}
</script>