<template>
    <app-layout title="Listado de notas">
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                Crear categoria
            </h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-xl sm:rounded-lg">
                   <form @submit.prevent="enviar">

                        <label class="block font-medium text-sm text-gray-700">
                            Nombre de la categoria
                        </label>

                        <textarea 
                            class="form-input w-full rounded-md shadow-sm"
                            v-model="form.category_name"
                        ></textarea>

                        <label class="block font-medium text-sm text-gray-700">
                            status
                        </label>

                        <textarea 
                            class="form-input w-full rounded-md shadow-sm"
                            v-model="form.category_status"
                            rows="8"
                        ></textarea>

                        <button 
                            class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded-md"
                        >Crear</button>
                        
                    </form>
                </div>
            </div>
        </div>
    </app-layout>
</template>

<script>
    import { defineComponent } from 'vue'
    import AppLayout from '@/Layouts/AppLayout.vue'

    export default defineComponent({
        components: {
            AppLayout,

        },
        data () {
            return{
                form: {
                    category_name: '',
                    category_status: '',
                }
            }
        },
        methods: {
            enviar(){
                this.$inertia.post(this.route('categorias.store', this.form))
            }
        },
    })
</script>
