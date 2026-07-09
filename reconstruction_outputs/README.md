# MapAnything Reconstruction Outputs

Metric 3D point clouds reconstructed by [MapAnything](https://github.com/facebookresearch/map-anything)
(`facebook/map-anything`) from the G2 robot captures in this repo.

For each capture, the 3 RGB views (head, hand_left, hand_right) were undistorted
(OpenCV Brown-Conrady, using the per-camera intrinsics JSONs) and jointly reconstructed
in a single multi-view inference with the undistorted intrinsics as input.

Files per capture:

| File | Description |
|------|-------------|
| `scene.glb` | Full merged colored point cloud (world frame = head camera, metric scale, OpenCV cam2world convention) |
| `scene.ply` | Same points in PLY format |
| `scene_filtered.glb` | Points within 2.0 m radius of the head camera (workspace only, far floor/walls removed), plus estimated camera frustum markers: head = red, hand_left = green, hand_right = blue |
| `scene_filtered.ply` | Same filtered points in PLY format |

View `.glb` files by dragging them into <https://gltf-viewer.donmccurdy.com/> or any glTF viewer;
`.ply` files open in CloudCompare / MeshLab / Open3D.
