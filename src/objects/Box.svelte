<script>
import Polygon from './Polygon.svelte'

export let position = {x: 0, y: 0, z: 0}
export let size = {x: 0, y: 0, z: 0}
export let colors = ['#48B056', '#008A25', '#2B9D3D']

$: polygons = [
  [
    {x: size.x + position.x, y: position.y, z: position.z},
    {x: size.x + position.x, y: size.y + position.y, z: position.z},
    {x: size.x + position.x, y: size.y + position.y, z: size.z + position.z},
    {x: size.x + position.x, y: position.y, z: size.z + position.z},
  ],
  [
    {x: position.x, y: size.y + position.y, z: position.z},
    {x: size.x + position.x, y: size.y + position.y, z: position.z},
    {x: size.x + position.x, y: size.y + position.y, z: size.z + position.z},
    {x: position.x, y: size.y + position.y, z: size.z + position.z},
  ],
  [
    {x: position.x, y: position.y, z: size.z + position.z},
    {x: size.x + position.x, y: position.y, z: size.z + position.z},
    {x: size.x + position.x, y: size.y + position.y, z: size.z + position.z},
    {x: position.x, y: size.y + position.y, z: size.z + position.z}
  ]
]

$: shadow = [
  {x: position.x, y: position.y, z: 0},
  {x: size.x + position.x, y: position.y, z: 0},
  {x: size.x + position.x, y: size.y + position.y, z: 0},
  {x: position.x, y: size.y + position.y, z: 0}
]
 
</script>

{#if position.z >= 0}
<Polygon points={shadow} color="rgba(0, 0, 0, 0.6)" />
{/if}
{#each polygons as points, i}
<Polygon {points} color="{colors[i]}" />
{/each}