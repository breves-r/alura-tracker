<template>
    <section>
        <strong :class="{ 'display': !isDone }">{{tempoDecorrido}}</strong>
    </section>
</template>

<script lang="ts">
    import { defineComponent } from 'vue'

    export default defineComponent({
        name: 'Cronometro',
        props: {
            tempoTotal: {
                type: Number,
                default: 0
            },
            isDone: {
                type: Boolean,
                default: false
            }
        },
        computed: {
            tempoDecorrido() : string{
                return new Date(this.tempoTotal * 1000).toISOString().substr(11,8)
            }
        }
    })
</script>

<style scoped>
    .display {
        color: var(--texto-primario);
    }
</style>