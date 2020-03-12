<script>
export let color = '#99FF00'
export let points = [
  {x: 0, y: 0, z: 0}
]

function xyzab (x, y, z) {
  return {
    a: (-3 * x) + (3 * y) + (0),
    b: ((3 * x) + (3 * y) + (-6 * z)) * Math.tan(30 * Math.PI/180)
  }
}

function pointsForSVG (points) {
  let result = ''
  for (const i in points) {
    const points3D = points[i]
    const points2D = xyzab(points3D.x, points3D.y, points3D.z)
    result = `${result} ${points2D.a},${points2D.b}`
  }
  return result
}
</script>

<style>
  polygon {
    transition: all 0.5s
  }
</style>

<polygon points="{pointsForSVG(points)}" fill="{color}" />