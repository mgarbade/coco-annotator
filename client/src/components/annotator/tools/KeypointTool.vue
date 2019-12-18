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
      console.log("KeypointTool.vue/onMouseDown")
      this.$parent.currentAnnotation.addKeypoint(event.point);
    },
    setVisibilityToInvisible(){
      this.keypoint.visibility
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
