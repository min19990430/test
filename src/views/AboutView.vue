<script setup lang="ts">
import DataTable from 'datatables.net-vue3';
import DataTablesCore from 'datatables.net';
import 'datatables.net-select';
import 'datatables.net-buttons';
import 'datatables.net-buttons/js/buttons.html5';
import 'datatables.net-responsive';
import Swal from 'sweetalert2';

DataTable.use(DataTablesCore);
const columns = [
  { data: 'name' },
  { data: 'position' },
  { data: 'office' },
  { data: 'extn' },
  { data: 'start_date' },
  { data: 'salary' },
];

const options = {
  responsive: true,
  select: true,
};

const showAlert = () => {
  Swal.fire({
    title: 'Hello!',
    text: 'This is a simple alert example.',
    icon: 'success',
    confirmButtonText: 'OK',
  });
};
</script>

<template>
  <div>
    <h1>Simple SweetAlert Example</h1>
    <button @click="showAlert">Click Me!</button>
  </div>
  <div>
    <DataTable
      :options="options"
      :columns="columns"
      ajax="/data.json"
      class="display"
      width="100%"
    >
      <thead>
        <tr>
          <th>Name</th>
          <th>Position</th>
          <th>Office</th>
          <th>Extn.</th>
          <th>Start date</th>
          <th>Salary</th>
        </tr>
      </thead>
      <tfoot>
        <tr>
          <th>Name</th>
          <th>Position</th>
          <th>Office</th>
          <th>Extn.</th>
          <th>Start date</th>
          <th>Salary</th>
        </tr>
      </tfoot>
    </DataTable>
  </div>
</template>



<style>
@import 'datatables.net-dt';
@import 'datatables.net-buttons-dt';
@import 'datatables.net-responsive-dt';
@import 'datatables.net-select-dt';
</style>
