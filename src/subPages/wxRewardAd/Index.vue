<template>
  <page-wraper :use-wx-ad="false">
    <div class="ad-completion-message">
      <div class="message-title">{{ $t('gan-xie-ni-yuan-yi-lai-guan-kan-guang-gao') }}</div>
      <div class="message-content">{{ $t('guan-kan-cheng-gong-jiu-yi-jing-cheng-gong-wei-wo-zhu-li') }}</div>
      <view class="button-group">
        <wd-button type="success" block @click="back">{{ $t('fan-hui-shi-yong') }}</wd-button>
        <wd-button type="error" block @click="showAd">{{ $t('guan-kan-shi-pin') }}</wd-button>
      </view>
    </div>
  </page-wraper>
</template>
<script setup lang="ts">
import { useRewardAd } from '@/store/useRewardAd'
import { onMounted } from 'vue'
const { createRewardVideoAd, showRewardAd } = useRewardAd()

onMounted(async () => {
  createRewardVideoAd()
})

function back() {
  uni.navigateBack()
}

function showAd() {
  showRewardAd()
}
</script>
<style lang="scss" scoped>
.ad-completion-message {
  text-align: center;
  padding: 20px;
}

.message-title {
  font-size: 24px;
  color: #4caf50;
}

.message-content {
  font-size: 16px;
  margin: 16px 0;
}

.continue-button {
  padding: 10px 20px;
  font-size: 16px;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.continue-button:hover {
  background-color: #0056b3;
}

.button-group {
  display: flex;
  justify-content: space-around;
  margin-top: 20px;
}
</style>
