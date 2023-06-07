<template>
  <v-app>
    <v-container>
      <v-btn @click="showDialog">open</v-btn>
      <upload-table :dialogShowed="dialogShowed" :configProps="config" @close-dialog="closeDialog"></upload-table>
    </v-container>
  </v-app>
</template>

<script>
import Table from "@/components/table.vue";
import UploadTable from "@/components/UploadTable.vue";
import MyDialog from "@/components/MyDialog.vue";
import MyPopup from "@/components/PopUp.vue";
export default {
  name: 'App',
  components: {MyPopup, UploadTable, Table, MyDialog },

  data() {
    return {
      dialogShowed: false,
      config: {
        parameters : {
          startRow: 1,
          amountRow: 1,
          sheet: 1,
        },
        columns: [
          { name: 'name', pos: '1', label: 'Наименование' },
          { name: 'short_name', pos: '2', label: 'Краткое название' },
          { name: 'struct_name', pos: '3', label: 'Структурное название' },
          { name: 'code', pos: '4', label: 'Код' },
          { name: 'sn', pos: '5', label: 'SN' },
          { name: 'barcode', pos: '6', label: 'Штрихкод' },
          { name: 'description', pos: '7', label: 'Описание' },
          { name: 'config', pos: '8', label: 'Конфиг' },
          { name: 'changes_date', pos: '9', label: 'Дата измененний' },
        ],
      },
    }
  },
  comments: {
    Table, UploadTable, MyDialog,
  },
  methods: {
    showDialog() {
      this.dialogShowed = true;
    },
    closeDialog() {
      this.dialogShowed = false;
    }
  },
};
</script>
