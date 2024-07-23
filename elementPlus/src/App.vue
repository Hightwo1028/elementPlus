<script setup></script>

<template>
  <h3>按鈕</h3>
  <el-button>默認按鈕</el-button>
  <el-button type="primary">主要按鈕</el-button>
  <el-button type="success">成功按鈕</el-button>
  <el-button type="info">訊息按鈕</el-button>
  <el-button type="warning">警告按鈕</el-button>
  <el-button type="danger">危險按鈕</el-button>

  <hr />
  <h3>按鈕屬性</h3>
  <el-button plain>樸素按鈕</el-button>
  <el-button round>圓角按鈕</el-button>
  <el-button circle>圓</el-button>
  <el-button disabled>禁用按鈕</el-button>
  <el-button loading>加載中</el-button>

  <hr />
  <h3>尺寸</h3>
  <el-button size="large">大型按鈕</el-button>
  <el-button>默認按鈕</el-button>
  <el-button size="small">小型按鈕</el-button>

  <h3>圖標</h3>
        <el-icon><Plus /></el-icon>
        <el-icon><Edit /></el-icon>
        <el-icon><Delete /></el-icon>
        <el-icon class="is-loading"><Loading /></el-icon>

        <hr>
        <h3>屬性</h3>
        <el-icon size="30" color="red"><Search /></el-icon>

        <hr>
        <h3>按鈕</h3>
        <el-button type="primary">
            <el-icon><Search /></el-icon>
            <span> 搜索 </span>
        </el-button>

        <el-button type="primary">
            <el-icon><Search /></el-icon>
        </el-button>

        <el-button type="primary" circle>
            <el-icon><Search /></el-icon>
        </el-button>

        <hr>
        <h3>按鈕組</h3>
        <el-button-group>
            <el-button type="primary">
                <el-icon><Plus /></el-icon>
            </el-button>

            <el-button type="primary">
                <el-icon><Edit /></el-icon>
            </el-button>

            <el-button type="primary">
                <el-icon><Delete /></el-icon>
            </el-button>
        </el-button-group>
</template>

<style scoped></style>
