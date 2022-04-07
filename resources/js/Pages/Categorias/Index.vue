<template>
    <app-layout title="Listado de notas">
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                Categorias
            </h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-xl sm:rounded-lg">
                    <inertia-link :href="route('categorias.create')">
                        Crear
                   </inertia-link>
                        <table>
                            <tr v-for="categoria in categorias" :key="categoria.id">
                                <td>
                                    {{categoria.category_name}}
                                </td>
                                <td>
                                    {{categoria.category_status}}
                                </td>
                                <!--<td>
                                    <inertia-link :href="route('noticias.show', nota.id)">
                                        ver
                                    </inertia-link>
                                </td> -->
                            </tr>
                        </table>
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
        props:{
            categorias:Array,
        }
    })
</script>
