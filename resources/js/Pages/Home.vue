<script setup>
import { Head } from '@inertiajs/vue3'
import Table from './Components/Table.vue'
import Create from './Components/Create.vue';

defineProps({ users: Object })

</script>

<template>
    <div data-theme="dark">
        <div class="min-h-screen bg-base-100">
            <div class="p-8 flex flex-col gap-3">
                <div>
                    <Create />
                </div>
                <div class="card shadow-xl">
                    <Table :users="users" />
                </div>
            </div>
        </div>
    </div>
</template>