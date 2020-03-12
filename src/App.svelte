<script>
import Box from './objects/Box.svelte'

let position = {x: 0, y: 0, z: 0}
let size = {x: 10, y: 10, z: 10}
let colors = ['#48B056', '#008A25', '#2B9D3D']
</script>

<style>
svg {
	background-color: rgb(196, 231, 182);
}
</style>

<div class="container">
	<div class="grid">
		<div class="col-6">
			<svg viewBox="-75 -100 200 200">
				<Box {position} {size} {colors} />
			</svg>
		</div>
		<div class="col-6">
			<div>Позиция</div>
			<label>
				<span>x</span>
				<input type="number" bind:value={position.x} />
			</label>
			<label>
				<span>y</span>
				<input type="number" bind:value={position.y} />
			</label>
			<label>
				<span>z</span>
				<input type="number" bind:value={position.z} />
			</label>
			<div class="mt-2">Габариты</div>
			<label>
				<span>x</span>
				<input type="number" bind:value={size.x} />
			</label>
			<label>
				<span>y</span>
				<input type="number" bind:value={size.y} />
			</label>
			<label>
				<span>z</span>
				<input type="number" bind:value={size.z} />
			</label>
		</div>
	</div>
</div>
