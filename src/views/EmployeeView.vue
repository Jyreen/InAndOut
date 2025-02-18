<template>
    <div>
        <div class="employee-container">
        <div class="header-row">
            <el-label style="font-size: xx-large;">Employees</el-label>
            <el-icon><Edit /></el-icon>
            <el-button type="primary" @click="centerDialogVisible = true">Add Employee</el-button>
        </div>

        <el-collapse v-model="activeNames" @change="handleChange">
            <el-collapse-item title="Filter Employees" name="1">
                <div class="filter-row">
        <el-select v-model="value" placeholder="Select" style="width: 240px">
        <el-option
            v-for="item in options"
            :key="item.value"
            :label="item.label"
            :value="item.value"
        />
        </el-select>
        </div>
        </el-collapse-item>
            </el-collapse>
        </div>

    <el-table :data="tableData" style="width: 100%">
        <el-table-column prop="date" label="No"/>
        <el-table-column prop="fname" label="First Name" width="180" />
        <el-table-column prop="lname" label="Last Name" width="180" />
        <el-table-column prop="role" label="First Name" width="180" />
        <el-table-column prop="address" label="Email Address" width="180" />
        <el-table-column label="Action" width="180">
            <template #default="scope">
                <el-button type="primary" size="small" >Edit </el-button>
                <el-button size="small" type="danger">Delete </el-button>
            </template>
        </el-table-column>
    </el-table>
    <el-pagination
      v-model:current-page="currentPage3"
      v-model:page-size="pageSize3"
      :size="size"
      :disabled="disabled"
      :background="background"
      layout="prev, pager, next, jumper"
      :total="100"
      @size-change="handleSizeChange"
      @current-change="handleCurrentChange"
    />

    <el-dialog v-model="centerDialogVisible" title="Add Employee" width="500" center>
    <span>
        <el-label>Employee:  </el-label>
        <el-select
        v-model="value"
        filterable
        remote
        reserve-keyword
        placeholder="Employee"
        :remote-method="remoteMethod"
        :loading="loading"
        style="width: 240px">
        <el-option
          v-for="item in options"
          :key="item.value"
          :label="item.label"
          :value="item.value"
        />
      </el-select>
      <br>
      <br>
      <el-label> Assign Role: </el-label>
      <el-select
    v-model="value"
    clearable
    placeholder="Role"
    style="width: 240px">
    <el-option
      v-for="item in options"
      :key="item.value"
      :label="item.label"
      :value="item.value"
    />
  </el-select>
    </span>
    <template #footer>
      <div class="dialog-footer">
        <el-button @click="centerDialogVisible = false">Cancel</el-button>
        <el-button type="primary" @click="centerDialogVisible = false">
          Add
        </el-button>
      </div>
    </template>
  </el-dialog>

    </div>
  </template>
  
<script>
import { defineComponent } from 'vue';


export default defineComponent({
    data() {
        return{
            centerDialogVisible: false,
        }
    },
})
</script>
  
<style>
.employee-container {
  display: flex;
  flex-direction: column;
  gap: 15px; /* Adds spacing between layers */
}

.header-row {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 15px; 
}

.search-select {
  width: 240px;
}

.filter-row {
  display: flex;
  align-items: center;
  gap: 10px; 
}

.filter-label {
  font-size: 14px;
}

.filter-select {
  width: 240px;
}
</style>