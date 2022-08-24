<script>
import TimelineItem from "../components/TimelineItem.vue";
import timelineData from "../data.json";

export default {
  components: {
    TimelineItem,
  },
  data() {
    return {
      timelineData,
    };
  },
};
</script>

<template>
  <h1>Timeline with Vue</h1>
  <div class="timeline-container">
    <TimelineItem
      v-for="item in timelineData"
      :key="item._id"
      :id="item._id"
      :registered="item.registered"
      :about="item.about"
      :first_name="item.name.first"
      :last_name="item.name.last"
      :tags="item.tags"
    >
    </TimelineItem>
  </div>
</template>

<style scoped>
.timeline-container {
  display: flex;
  flex-direction: column;
  position: relative;
  margin: 40px 0;
}

.timeline-container::after {
  background-color: #114c84;
  content: "";
  position: absolute;
  left: calc(50% - 2px);
  width: 4px;
  height: 100%;
}
</style>
