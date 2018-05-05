<template>
  <div>
    <h1>イベント一覧</h1>
    <ul>
      <li v-for="event in events" v-bind:key="event.event_id">
        {{ event.started_at }}
        <a :href="event.event_url" target="_blank">{{ event.title }}</a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  async asyncData({ params, app}) {
    const result = await app.$axios.$get('https://connpass.com/api/v1/event/?keyword=javascript')
    return {events: result.events}
  }
}
</script>
