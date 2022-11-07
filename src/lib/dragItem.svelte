<script>
  import { draggable } from "@neodrag/svelte";
  export let item;
  export let answer;
</script>

<div
  class="{answer
    ? ' bg-teal-600'
    : 'bg-blue-600'} p-2 rounded-md shadow-md text-white block w-64 transition-all ease-out cursor-move h-[120px] hover:shadow-xl hover:opacity-80"
  use:draggable={{
    position: { x: 1, y: 2 },
  }}
>
  <p class="font-bold">{item.name.split(":")[0]}</p>
  <p class=" text-xs">{item.name.split(":")[1]}</p>
</div>
