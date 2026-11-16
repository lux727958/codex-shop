<script setup>
import { reactive, ref } from 'vue'

const dialog = ref(null)
const nameInput = ref(null)
const dateInput = ref(null)
const today = ref(localDate())
const result = ref('')
const form = reactive({ name: '', date: today.value, time: '11:30', guests: '2 位' })
const times = ['11:30', '12:30', '17:30', '18:30', '19:30']
const guestOptions = ['2 位', '1 位', '3 位', '4 位', '5–6 位']

function localDate() {
  const date = new Date()
  return `${date.getFullYear()}-${String(date.getMonth() + 1).padStart(2, '0')}-${String(date.getDate()).padStart(2, '0')}`
}

function open() {
  today.value = localDate()
  if (form.date < today.value) form.date = today.value
  result.value = ''
  nameInput.value?.setCustomValidity('')
  dateInput.value?.setCustomValidity('')
  if (!dialog.value.open) dialog.value.showModal()
}

function closeOnBackdrop(event) {
  if (event.target !== dialog.value) return
  const rect = dialog.value.getBoundingClientRect()
  if (event.clientX < rect.left || event.clientX > rect.right || event.clientY < rect.top || event.clientY > rect.bottom) dialog.value.close()
}

function submit() {
  nameInput.value.setCustomValidity(form.name.trim() ? '' : '请输入您的称呼，不能仅包含空格')
  dateInput.value.setCustomValidity(form.date >= localDate() ? '' : '请选择今天或之后的日期')
  if (!nameInput.value.reportValidity() || !dateInput.value.reportValidity()) return
  result.value = `${form.name.trim()}，已生成您的预约意向：${form.date} ${form.time}，${form.guests}。此为演示，尚未向门店提交，请待门店联系方式公布后确认订位。`
}

defineExpose({ open })
</script>

<template>
  <dialog id="booking" ref="dialog" aria-labelledby="booking-title" aria-describedby="booking-description" @click="closeOnBackdrop">
    <button class="close" aria-label="关闭预约弹窗" @click="dialog.close()">×</button>
    <div class="eyebrow">A MOMENT TOGETHER</div>
    <h2 id="booking-title">预约一份好时光</h2>
    <p id="booking-description">此为订位体验演示，不会向餐厅发送预约。</p>
    <form v-show="!result" id="booking-form" @submit.prevent="submit">
      <label>您的称呼<input ref="nameInput" v-model="form.name" name="name" required placeholder="怎么称呼您" maxlength="30" @input="nameInput.setCustomValidity('')"></label>
      <div class="form-row">
        <label>用餐日期<input ref="dateInput" v-model="form.date" type="date" name="date" :min="today" required @input="dateInput.setCustomValidity('')"></label>
        <label>用餐时间<select v-model="form.time" name="time"><option v-for="time in times" :key="time">{{ time }}</option></select></label>
      </div>
      <label>用餐人数<select v-model="form.guests" name="guests"><option v-for="guests in guestOptions" :key="guests">{{ guests }}</option></select></label>
      <button class="button" type="submit">生成预约意向 →</button>
    </form>
    <div v-show="result" id="booking-result" role="status">{{ result }}</div>
  </dialog>
</template>
