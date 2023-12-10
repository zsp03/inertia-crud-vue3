<script setup>
import { router } from '@inertiajs/vue3';

const props = defineProps({ user: Object })

let name = props.user.name
let email = props.user.email

function update(id) {
    router.put(`/users/${id}`, {
        name: name,
        email: email
    })
    document.getElementById(`edit-modal-${id}`).close()
}

</script>

<template>
    <dialog :id="`edit-modal-${user.id}`" class="modal">
        <div class="modal-box">
            <form method="dialog">
                <button class="btn btn-sm btn-circle btn-ghost absolute right-2 top-2">✕</button>
            </form>
            <div class="flex flex-col items-center w-full px-12 gap-4">
                <div class="w-full">
                    <input class="input input-bordered w-full" :placeholder=user.name v-model="name" />
                </div>
                <div class="w-full">
                    <input class="input input-bordered w-full" :placeholder=user.email v-model="email" />
                </div>
                <div class="indicator self-center">
                    <button @click="update(user.id)" class="btn join-item">Edit</button>
                </div>
            </div>
        </div>
    </dialog>
</template>