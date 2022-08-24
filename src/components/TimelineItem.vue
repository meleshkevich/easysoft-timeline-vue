<script>
export default {
  name: "TimelineItem",
  props: {
    id: String,
    registered: String,
    first_name: String,
    last_name: String,
    about: String,
    tags: Array,
  },
};
</script>

<template>
  <div class="timeline-item">
    <div class="timeline-item-content">
      <small>
        <strong>Data id: {{ id }}</strong>
      </small>
      <p>{{ registered }}</p>
      <p>
        Name:
        {{ first_name }} {{ last_name }}
      </p>
      <p>Description: {{ about }}</p>
      <p>
        Tags:
        <small v-for="(tag, i) in tags" :key="i">{{ tag }}, </small>
      </p>
      <div class="circle"></div>
    </div>
  </div>
</template>
<style scoped>
.timeline-item {
  display: flex;
  justify-content: flex-end;
  padding-right: 30px;
  position: relative;
  margin: 20px 0;
  width: 50%;
}

.timeline-item:nth-child(odd) {
  align-self: flex-end;
  justify-content: flex-start;
  padding-left: 30px;
  padding-right: 0;
  text-align: left;
}

.timeline-item-content {
  box-shadow: 0 0 5px rgba(0, 0, 0, 0.3);
  border-radius: 5px;
  background-color: #fff;
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  padding: 30px;
  position: relative;
  width: 800px;
  max-width: 100%;
  text-align: right;
}

.timeline-item-content::after {
  content: " ";
  background-color: #fff;
  box-shadow: 1px -1px 1px rgba(0, 0, 0, 0.2);
  position: absolute;
  right: -7.5px;
  top: calc(50% - 7.5px);
  transform: rotate(45deg);
  width: 15px;
  height: 15px;
}

.timeline-item:nth-child(odd) .timeline-item-content {
  text-align: left;
  align-items: flex-start;
}

.timeline-item:nth-child(odd) .timeline-item-content::after {
  right: auto;
  left: -7.5px;
  box-shadow: -1px 1px 1px rgba(0, 0, 0, 0.2);
}
.timeline-item-content .tag {
  color: #fff;
  font-size: 12px;
  font-weight: bold;
  top: 5px;
  left: 5px;
  letter-spacing: 1px;
  padding: 5px;
  position: absolute;
}

.timeline-item-content p {
  font-size: 16px;
  line-height: 24px;
  margin: 15px 0;
  max-width: 250px;
}

.timeline-item-content .circle {
  background-color: #fff;
  border: 3px solid #114c84;
  border-radius: 50%;
  position: absolute;
  top: calc(50% - 10px);
  right: -15px;
  width: 20px;
  height: 20px;
  z-index: 100;
}

.timeline-item:nth-child(odd) .timeline-item-content .circle {
  right: auto;
  left: -40px;
}
.timeline-item:nth-child(even) .timeline-item-content .circle {
  right: auto;
  right: -40px;
}
@media only screen and (max-width: 1023px) {
  .timeline-item-content {
    max-width: 100%;
  }
}

@media only screen and (max-width: 767px) {
  .timeline-item-content,
  .timeline-item:nth-child(odd) .timeline-item-content {
    padding: 15px 10px;
    text-align: center;
    align-items: center;
  }

  .timeline-item-content time {
    margin-top: 20px;
  }
}
</style>
