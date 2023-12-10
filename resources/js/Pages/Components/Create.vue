<script setup>

import { router } from '@inertiajs/vue3';

let name = ''
let email = ''

function create() {
    router.post('/users', {
        name: name,
        email: email
    })

    name = ''
    email = ''
}

</script>

<template>
    <div class="join">
        <div>
            <div>
                <input class="input input-bordered join-item" placeholder="Name" v-model="name" />
            </div>
        </div>
        <div>
            <input class="input input-bordered join-item" placeholder="Email" v-model="email" />
        </div>
        <div class="indicator">
            <button @click="create" class="btn join-item">Create</button>
        </div>
    </div>
</template>