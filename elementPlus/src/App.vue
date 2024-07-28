<script setup>
  import { ElMessage, ElMessageBox, ElNotification } from "element-plus";
  import { reactive, ref } from "vue";

  // 訊息
  const openMsg = () => {
    ElMessage({
      type: "success", // success | warning | info | error
      message: "hightwocode.com",
      showClose: true,
    });
  };

  // 確認框
  const openConfirm = () => {
    ElMessageBox.confirm("確認刪除?", "標題", {
      type: "warning", // success | warning | info | error
      confirmButtonText: "確認",
      cancelButtonText: "取消",
    })
      .then(() => {
        console.log("確認");
      })
      .catch(() => {
        console.log("取消");
      });
  };

  // 通知
  const openNotifiy = () => {
    ElNotification({
      title: "標題",
      message: "嗨兔摳頂",
      duration: 1500, // 展示時間 [單位:毫秒]
    });
  };

  // 通知2
  const openNotifiy2 = () => {
    ElNotification({
      type: "success", // success | warning | info | error
      title: "標題",
      message: "hightwo.com",
      duration: 1500, // 展示時間 [單位:毫秒]
      position: "bottom-right",
    });
  };
  //默認選中的菜單索引
  const selectedIndex = ref("2-2");
  //選中菜單觸發的回調
  const selected = (index, indexPath) => {
    console.log("index:", index, "indexPath:", indexPath);
  };
  //默認展開的菜單索引
  const defaultOpeneds = ref(["1", "0"]);

  const userCommand = (command) => {
    console.log("command:", command);
  };
</script>

<template>
  <el-button @click="openMsg">訊息</el-button>
  <el-button @click="openConfirm">確認框</el-button>
  <el-button @click="openNotifiy">通知框1</el-button>
  <el-button @click="openNotifiy2">通知框2</el-button>

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
  <el-icon>
    <Plus />
  </el-icon>
  <el-icon>
    <Edit />
  </el-icon>
  <el-icon>
    <Delete />
  </el-icon>
  <el-icon class="is-loading">
    <Loading />
  </el-icon>

  <hr />
  <h3>屬性</h3>
  <el-icon size="30" color="red">
    <Search />
  </el-icon>

  <hr />
  <h3>按鈕</h3>
  <el-button type="primary">
    <el-icon>
      <Search />
    </el-icon>
    <span> 搜索 </span>
  </el-button>

  <el-button type="primary">
    <el-icon>
      <Search />
    </el-icon>
  </el-button>

  <el-button type="primary" circle>
    <el-icon>
      <Search />
    </el-icon>
  </el-button>

  <hr />
  <h3>按鈕組</h3>
  <el-button-group>
    <el-button type="primary">
      <el-icon>
        <Plus />
      </el-icon>
    </el-button>

    <el-button type="primary">
      <el-icon>
        <Edit />
      </el-icon>
    </el-button>

    <el-button type="primary">
      ˋㄒ
      <el-icon>
        <Delete />
      </el-icon>
    </el-button>
  </el-button-group>

  <!-- guided tour //navbar -->
  <h3>水平導覽</h3>
  <el-menu mode="horizontal" :default-active="selectedIndex" @select="selected">
    <el-menu-item index="1">嗨兔摳頂</el-menu-item>
    <el-sub-menu index="2">
      <template #title>我的工作臺</template>
      <el-menu-item index="2-1">選項1</el-menu-item>
      <el-menu-item index="2-2">選項2</el-menu-item>
      <el-menu-item index="2-3">選項3</el-menu-item>
    </el-sub-menu>
    <el-menu-item index="3">消息中心</el-menu-item>
    <el-menu-item index="4">訂單管理</el-menu-item>
  </el-menu>

  <h3>水平導覽列 自定義樣式</h3>
  <!-- mode="horizontal" -->
  <el-menu
    :default-active="selectedIndex"
    @select="selected"
    background-color="#545c64"
    text-color="#fff"
    active-text-color="#ffd04b"
  >
    <!-- style="height: 375px; width: 600px" -->
    <el-menu-item index="1">嗨兔摳頂</el-menu-item>
    <el-sub-menu index="2">
      <template #title>我的工作臺</template>
      <el-menu-item index="2-1">選項1</el-menu-item>
      <el-menu-item index="2-2">選項2</el-menu-item>
      <el-menu-item index="2-3">選項3</el-menu-item>
    </el-sub-menu>
    <el-menu-item index="3">消息中心</el-menu-item>
    <el-menu-item index="4">訂單管理</el-menu-item>
  </el-menu>

  <h3>麵包屑</h3>
  <el-breadcrumb separator="|||">
    <el-breadcrumb-item><a href="#">首頁</a></el-breadcrumb-item>
    <el-breadcrumb-item>嗨兔摳頂</el-breadcrumb-item>
    <el-breadcrumb-item>hightwocode.com</el-breadcrumb-item>
  </el-breadcrumb>

  <h3>下拉菜單</h3>
  <el-dropdown @command="userCommand">
    <span>
      個人中心 <el-icon><User /></el-icon>
    </span>
    <template #dropdown>
      <el-dropdown-menu>
        <el-dropdown-item command="order">訂單</el-dropdown-item>
        <el-dropdown-item command="logout">登出</el-dropdown-item>
      </el-dropdown-menu>
    </template>
  </el-dropdown>
</template>

<style scoped></style>
