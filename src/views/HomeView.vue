<template>
  <div>
    <el-row :gutter="1">
      <el-col :span="10">
        <div class="statistic-card">
          <el-statistic :value="98500">
            <template #title>
              <div class="stat-title">
                Daily active users
                <el-tooltip
                  effect="dark"
                  content="Number of users who logged into the product in one day"
                  placement="top"
                >
                  <el-icon class="tooltip-icon">
                    <Warning />
                  </el-icon>
                </el-tooltip>
              </div>
            </template>
          </el-statistic>
          <div class="statistic-footer">
            <div class="footer-item">
              <span>than yesterday</span>
              <span class="green">
                24%
                <el-icon>
                  <CaretTop />
                </el-icon>
              </span>
            </div>
          </div>
        </div>
      </el-col>
      <el-col :span="10">
        <div class="statistic-card">
          <el-statistic :value="693700">
            <template #title>
              <div class="stat-title">
                Monthly Active Users
                <el-tooltip
                  effect="dark"
                  content="Number of users who logged into the product in one month"
                  placement="top"
                >
                  <el-icon class="tooltip-icon">
                    <Warning />
                  </el-icon>
                </el-tooltip>
              </div>
            </template>
          </el-statistic>
          <div class="statistic-footer">
            <div class="footer-item">
              <span>month on month</span>
              <span class="red">
                12%
                <el-icon>
                  <CaretBottom />
                </el-icon>
              </span>
            </div>
          </div>
        </div>
      </el-col>
      <el-col :span="10">
        <div class="statistic-card">
          <el-statistic :value="72000">
            <template #title>
              <div class="stat-title">New transactions today</div>
            </template>
          </el-statistic>
          <div class="statistic-footer">
            <div class="footer-item">
              <span>than yesterday</span>
              <span class="green">
                16%
                <el-icon>
                  <CaretTop />
                </el-icon>
              </span>
            </div>
            <div class="footer-item">
              <el-icon class="arrow-icon">
                <ArrowRight />
              </el-icon>
            </div>
          </div>
        </div>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import { ArrowRight, CaretBottom, CaretTop, Warning } from '@element-plus/icons-vue'

export default {
  components: {
    ArrowRight,
    CaretBottom,
    CaretTop,
    Warning,
  },
}
</script>

<style scoped>
.el-statistic {
  --el-statistic-content-font-size: 28px;
}

.stat-title {
  display: flex;
  align-items: center;
  gap: 4px;
}

.tooltip-icon {
  margin-left: 4px;
  font-size: 14px;
}

.statistic-footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 12px;
  color: var(--el-text-color-regular);
  margin-top: 16px;
}

.statistic-footer .footer-item {
  display: flex;
  align-items: center;
  gap: 4px;
}

.green {
  color: var(--el-color-success);
}
.red {
  color: var(--el-color-error);
}

.el-row {
  display: flex;
  justify-content: space-between;
  width: 100%;
  margin-top: 80px;
}

.el-col {
  display: flex;
  justify-content: center;
}
.arrow-icon {
  font-size: 14px;
}
</style>
