# NoLa posetraces

Posetrace videos and camera poses for the ULB NoLa (non-Lambertian) test sequences
**Aquarium** and **BelgianBeer**, rendered from per-frame Gaussian-splat reconstructions
(gsplat simple_trainer, 30k steps, full resolution, shared rig poses). Browse them at
https://lisa-vr.github.io/nola-posetraces/.

Every trace comes in two versions: `_clean` (floaters removed: a Gaussian must weigh at least
0.5 px in at least 4 rig views, and lie at world z in [4, 11]) and `_raw` (the training as is).
This repository always holds only the latest snapshot (one commit, force-pushed).

Poses (`poses/<Scene>/<trace>.{json,csv}`): 300 frames at 30 fps in the dataset's original COLMAP
world, OpenCV camera (x right, y down, z forward). JSON: 4x4 camera-to-world matrix plus fx, fy,
cx, cy for a 1920x1080 image. CSV: camera centre, camera-to-world quaternion (w, x, y, z), intrinsics.
Pose t is rendered from the model of capture frame t.

## License
CC BY-NC-SA 4.0 (https://creativecommons.org/licenses/by-nc-sa/4.0/). The test sequences are
provided by Hamed Razavi Khosroshahi (ULB), Daniele Bonatto (ULB), Gun Bang (ETRI) and Gauthier
Lafruit (ULB). Any publication or use should refer to:

- "[GSC][JEE6.1] Non-Lambertian test sequences: NoLa BelgianBeer and NoLa Aquarium", Hamed Razavi
  Khosroshahi, Daniele Bonatto, Gun Bang, Gauthier Lafruit. ISO/IEC JTC 1/SC 29/WG 7 m78812,
  October 2026, Hangzhou, China.
- "[CINVR][GSC][JEE6.1] Non-Lambertian dataset Aquarium: a Gaussian Splats failure case", Hamed
  Razavi Khosroshahi, Daniele Bonatto, Gun Bang, Gauthier Lafruit. ISO/IEC JTC 1/SC 29/WG 7 m78875,
  October 2026, Hangzhou, China.
