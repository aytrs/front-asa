<template>
  <FullCalendar :options="calendarOptions" />
</template>

<script setup>
import FullCalendar from '@fullcalendar/vue3'
import dayGridPlugin from '@fullcalendar/daygrid'
import ptBrLocale from '@fullcalendar/core/locales/pt-br'

const calendarOptions = {
  plugins: [dayGridPlugin],
  initialView: 'dayGridMonth',
  locale: ptBrLocale,
  headerToolbar: {
    left: 'prev,next today',
    center: 'title',
    right: 'dayGridMonth'
  },
  style: {
    height: '20px',
    width: '30px',
  },
  events: [
    { title: 'Evento de Teste', date: '2025-06-13' }
  ]
}
</script>
