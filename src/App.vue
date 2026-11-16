<script setup>
import { ref } from 'vue'
import SiteHeader from './components/SiteHeader.vue'
import HeroSection from './components/HeroSection.vue'
import MenuSection from './components/MenuSection.vue'
import StorySection from './components/StorySection.vue'
import VisitSection from './components/VisitSection.vue'
import SiteFooter from './components/SiteFooter.vue'
import BookingDialog from './components/BookingDialog.vue'

const booking = ref(null)
const openBooking = () => booking.value.open()
</script>

<template>
  <SiteHeader @book="openBooking" />
  <main>
    <HeroSection @book="openBooking" />
    <MenuSection />
    <StorySection />
    <VisitSection @book="openBooking" />
  </main>
  <SiteFooter />
  <BookingDialog ref="booking" />
</template>
