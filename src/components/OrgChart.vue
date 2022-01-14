<template>
  <div id="tree" ref="tree"></div>
</template>

        <script>
import OrgChart from "@balkangraph/orgchart.js";
OrgChart.templates.ana.field_1 =
  '<text data-width="130" data-text-overflow="multiline" style="font-size: 14px; font-weight:bold;" fill="#1A237E" x="230" y="30" text-anchor="end" class="field_1">{val}</text>';
OrgChart.templates.ana.field_0 =
  '<text width="230" style="font-size: 20px;" fill="white" x="125" y="95" text-anchor="middle" class="field_0">{val}</text>';
export default {
  name: "tree",
  data() {
    return {
      nodes: [
        {
          id: 1,
          name: "วนัทปรียา สวัสดิวงชัย",
          title: "ย่า",
          img: "https://cdn.balkan.app/shared/2.jpg",
        },
        {
          id: 2,
          pid: 1,
          tags: ["partner"],
          name: "ทินกร สวัสดิวงชัย",
          title: "ปู่",
          img: "https://cdn.balkan.app/shared/3.jpg",
        },
        {
          id: 3,
          pid: 1,
          ppid: 2,
          name: "อธิชาติ สวัสดิวงชัย",
          title: "ลูกคนที่ 1",
          img: "https://cdn.balkan.app/shared/1.jpg",
        },
        {
          id: 4,
          pid: 1,
          ppid: 2,
          name: "ชิตชัย สวัสดิวงชัย",
          title: "ลูกคนที่ 2",
          img: "https://cdn.balkan.app/shared/5.jpg",
        },
        {
          id: 5,
          pid: 1,
          ppid: 2,
          name: "วรเชษฐ์ สวัสดิวงชัย",
          title: "ลูกคนที่ 3",
          img: "https://cdn.balkan.app/shared/9.jpg",
        },
        {
          id: 6,
          pid: 3,
          tags: ["partner"],
          name: "ศินีนุช รัชโน",
          title: "ภรรยาของลูกคนที่ 1",
          img: "https://cdn.balkan.app/shared/4.jpg",
        },
        {
          id: 7,
          pid: 5,
          tags: ["partner"],
          name: "นิสาชล สวัสดิวงชัย",
          title: "ภรรยาของลูกคนที่ 3",
          img: "https://cdn.balkan.app/shared/8.jpg",
        },
        {
          id: 8,
          pid: 3,
          ppid: 6,
          name: "สุภัสสรา สวัสดิวงชัย",
          title: "หลานคนที่ 1",
          img: "https://cdn.balkan.app/shared/6.jpg",
        },
        {
          id: 9,
          pid: 3,
          ppid: 6,
          name: "ฐิติวุฒิ สวัสดิวงชัย",
          title: "หลานคนที่ 2",
          img: "https://cdn.balkan.app/shared/7.jpg",
        },
        {
          id: 10,
          pid: 5,
          ppid: 7,
          name: "ศุภณัฐ สวัสดิวงชัย",
          title: "หลานคนที่ 3",
          img: "https://cdn.balkan.app/shared/13.jpg",
        },
        {
          id: 11,
          pid: 10,
          tags: ["partner"],
          name: "ณิชตา ตะโพธิ์",
          title: "ภรรยาของหลานคนที่ 3",
          img: "https://cdn.balkan.app/shared/14.jpg",
        },
      ],
    };
  },

  methods: {
    mytree: function (domEl, x) {
      this.chart = new OrgChart(domEl, {
        enableDragDrop: true,
        nodes: x,
        nodeBinding: {
          field_0: "name",
          field_1: "title",
          img_0: "img",
          link_field_0: "status",
          scaleInitial: 0.5,
        },
      });
    },
  },

  mounted() {
    this.mytree(this.$refs.tree, this.nodes);
  },
};
</script>

        <style>
[data-n-id] rect {
  fill: #448AFF;
}
[data-n-id] rect:hover {
  filter: drop-shadow(4px 5px 5px #aeaeae);
}
</style>