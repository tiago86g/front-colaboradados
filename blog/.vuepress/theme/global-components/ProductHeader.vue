<template>
  <header>
    <time :class="$style.timestamp" :datetime="data.date">{{ date }}</time>
    <p :class="$style.title">
      {{ product }} | <span :class="$style.edition">{{ data.edition }}</span>
    </p>
  </header>
</template>

<script>
import moment from "moment";
import { formatArtcileTimestap } from "@helpers/patterns";

export default {
  name: "ProductHeader",
  props: ["product", "data"],
  computed: {
    date() {
      return moment(this.data.date).format(formatArtcileTimestap);
    },
  },
};
</script>

<style lang="scss" module>
.title {
  margin: 0;
}

.edition {
  font-weight: 600;
}

.timestamp {
  display: block;
  font-size: 0.8em;
  margin: 1rem 0 1rem;
}
</style>
