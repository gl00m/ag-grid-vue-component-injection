<template>
    <div :style="{backgroundColor: params.value}" >-</div>
</template>

<script lang="ts">
    import { ICellRendererParams } from 'ag-grid-community';
    import {Component, Vue} from 'vue-property-decorator'

    @Component
    export default class IconCell extends Vue {
        params!: ICellRendererParams
    }
</script>
