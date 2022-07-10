<template>
  <canvas
    id="myCanvas"
    ref="canvas"
    :width="width"
    :height="height"
    @click="draw($event)"
  ></canvas>
  <br />
  <button @click="handleDownload">Download</button>
  <button @click="handleSave">Save</button>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      canvasContext: null,
      isDrawing: false,
    };
  },
  props: ["width", "height", "imageName"],
  mounted() {
    this.canvasContext = this.$refs.canvas.getContext("2d");
    // Attach event listeners
    this.$refs.canvas.addEventListener("mousedown", this.onMouseDown);
    this.$refs.canvas.addEventListener("mousemove", this.onMouseMove);
    this.$refs.canvas.addEventListener("mouseup", this.onMouseUp);
  },
  unmounted() {
    // TODO: clear event listeners
  },
  methods: {
    // Begin drawing by moving drawing cursor to mouse coordinates and
    // beginning a new drawing path.
    onMouseDown(e) {
      this.isDrawing = true;
      const pos = this.getMousePos(this.$refs.canvas, e);
      this.canvasContext.moveTo(pos.x, pos.y);
      this.canvasContext.beginPath();
    },
    // Continuously add a new point to the path and colour the last segment
    onMouseMove(e) {
      if (this.isDrawing) {
        const pos = this.getMousePos(this.$refs.canvas, e);
        this.canvasContext.lineTo(pos.x, pos.y);
        this.canvasContext.stroke();
      }
    },
    // Disables drawing when mouse is up
    onMouseUp() {
      this.isDrawing = false;
    },
    // Gets mouse position in x and y
    getMousePos(canvas, evt) {
      var rect = canvas.getBoundingClientRect();
      return {
        x: evt.clientX - rect.left,
        y: evt.clientY - rect.top,
      };
    },
    // Draws on mouse click
    draw(e) {
      const pos = this.getMousePos(this.$refs.canvas, e);
      this.drawPixel(pos.x, pos.y);
    },
    // Draws a pixel
    drawPixel(x, y) {
      this.canvasContext.beginPath();
      this.canvasContext.arc(x, y, 1, 0, Math.PI * 2, true);
      this.canvasContext.closePath();
      this.canvasContext.fill();
    },
    async handleSave() {
      const image = this.$refs.canvas
        .toDataURL("image/png")
        .replace("image/png", "image/octet-stream");
      // TODO: move to vuex
      try {
        const { data } = await axios.post("http://localhost:3000/images", {
          data: image,
          name: this.imageName,
        });
      } catch (error) {
        console.log(error);
      }
      // TODO: display notification
    },
    handleDownload() {
      const image = this.$refs.canvas
        .toDataURL("image/png")
        .replace("image/png", "image/octet-stream");
      // Create anchor element
      let element = document.createElement("a");
      const filename = `${this.imageName}.png`;
      element.setAttribute("href", image);
      element.setAttribute("download", filename);
      // Initiates download
      element.click();
    },
  },
};
</script>

<style>
#myCanvas {
  border: 1px solid #000;
  background: #fff;
  /* cursor: crosshair; */
}
</style>
