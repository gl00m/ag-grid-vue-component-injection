<template>
    <ag-grid-vue
            ref="agTable"
            style="height: 500px"
            class="ag-theme-alpine"
            v-on="$listeners"
            v-bind="$attrs"
            :column-types="columnTypes"
            :framework-components="frameworkComponents"
    />
</template>

<script lang="ts">
    import "ag-grid-community/styles/ag-grid.css";
    import "ag-grid-community/styles/ag-theme-alpine.css";
    import {Component, Vue} from "vue-property-decorator"
    import {AgGridVue} from "ag-grid-vue"
    import {ColDef} from "ag-grid-community"
    import ColorCell from "@/components/grid/ColorCell.vue"
    
    export const frameworkComponents = {
        ColorCell,
    }

    export const columnTypes: Record<string, ColDef> = {
        icon: {
            cellRenderer: 'ColorCell',
        },
    }

    @Component({
        components: {
            AgGridVue,
        }
    })
    export default class AgTable extends Vue {
        public frameworkComponents = frameworkComponents
        public columnTypes = columnTypes
    }
</script>