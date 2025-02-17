<template>
  <div>
    <el-row :gutter="16" justify="center">
      <el-col :xs="24" :sm="12" :md="8">
        <el-card class="card">
          <p>Total Shipments:</p>
          <h2>1,234</h2>
        </el-card>
      </el-col>
      <el-col :xs="24" :sm="12" :md="8">
        <el-card class="card">
          <p>Total Inbound:</p>
          <h2>1,234</h2>
        </el-card>
      </el-col>
      <el-col :xs="24" :sm="12" :md="8">
        <el-card class="card">
          <p>Total Outbound:</p>
          <h2>1,234</h2>
        </el-card>
      </el-col>
      <el-col :xs="24" :sm="12" :md="8">
        <el-card class="card">
          <p>Total Employees:</p>
          <h2>66</h2>
        </el-card>
      </el-col>
    </el-row>
  </div>
</template>

<style scoped>
.card {
  width: 100%;
  padding: 20px;
  border-radius: 8px;
  background-color: white;
  border: 1px solid #ddd;
  box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.1);
  text-align: center;
}

.el-row {
  display: flex;
  justify-content: center;
}

</style>
