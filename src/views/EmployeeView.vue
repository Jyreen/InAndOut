<template>
    <div>
        <div class="employee-container">
        <div class="header-row">
            <div class="filter-row">
                <h2 style="text-emphasis: bold;">Employees</h2>
                <el-select
                    v-model="searchValue"
                    filterable
                    remote
                    reserve-keyword
                    placeholder="Search..."
                    :remote-method="remoteMethod"
                    :loading="loading"
                    class="search-select"
                >
                    <el-option
                    v-for="item in options"
                    :key="item.value"
                    :label="item.label"
                    :value="item.value"
                    />
                </el-select>
            </div>
        <el-button type="primary">Add Employee</el-button>
        </div>

    <div class="filter-row">
      <label class="filter-label">Filter Employees</label>
      <el-select v-model="value" placeholder="Select" style="width: 240px">
      <el-option
        v-for="item in options"
        :key="item.value"
        :label="item.label"
        :value="item.value"
      />
    </el-select>
    </div>
  </div>

    <el-table :data="tableData" style="width: 100%">
        <el-table-column prop="date" label="No"/>
        <el-table-column prop="fname" label="First Name" width="180" />
        <el-table-column prop="lname" label="Last Name" width="180" />
            <el-table-column prop="role" label="First Name" width="180" />
            <el-table-column prop="address" label="Email Address" width="180" />
            <el-table-column prop="warehouse" label="Assigned Warehouse" width="180" />
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

    </div>
  </template>
  
  <script>

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