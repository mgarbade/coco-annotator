<script>
import tool from "@/mixins/toolBar/tool";

export default {
  name: "KeypointTool",
  mixins: [tool],
  props: {
    scale: {
      type: Number,
      default: 1
    },
    settings: {
      type: [Object, null],
      default: null
    }
  },
  data() {
    return {
      icon: "fa-map-marker",
      name: "Keypoints",
      cursor: "cell",
    };
  },
  methods: {
    export() {
      return {};
    },
    onMouseDown(event) {
      console.log("MG onMouseDown00")
      this.$parent.currentAnnotation.addKeypoint(event.point);
    },
    skipKeypoint() {
      this.$parent.currentAnnotation.skipKeypoint(new paper.Point(0, 0), 0);
      console.log("MARTIN has pressed skipKeypoint")
    }
  },
  computed: {
    isDisabled() {
      return this.$parent.current.annotation === -1;
    }
  },
  watch: {},
  created() {},
  mounted() {}
};
</script>
