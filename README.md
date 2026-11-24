# Model a V-Groove Drill Guide for 3D Printing

_AI disclosure: An AI assistant prepared this version from the Reactor 3D Team’s original tutorial and modeling screenshots._

This CAD exercise builds a 60 × 30 × 24 mm guide body with a full-length V-groove and a stepped seat for a separate metal sleeve. The sleeve reference fits flush and guides a nominal 6 mm bit. The workflow covers accurate sketch coordinates, a subtractive cut and a centered counterbore.

## 01. Create the body blank

Start a blank millimeter project in Solid Model mode. Create a cube and open its Cube history item. Name it Drill Guide Body, set width to 60 mm, depth to 30 mm and height to 24 mm, and set its world position and rotation to zero. X runs along the length, Y along the depth, and Z along the height. The bottom sits at Z0 and the top at Z24.

![The 60 × 30 × 24 mm body blank at world position zero](https://assets.reactor3d.xyz/tutorials-page/articles/3d-printed-drill-guide/image-b9025b97-3754-405e-b0dc-ba17bf30e43f-1600x900-90ded7c0cc0b.webp)

## 02. Round the four vertical corners

Select the four vertical outside edges in a single Fillet group. Orbit to reach the back edges as needed. Set the fillet size to 3 mm, keep the top and bottom perimeter edges out of the selection, and confirm.

![Four vertical edges selected for a 3 mm fillet](https://assets.reactor3d.xyz/tutorials-page/articles/3d-printed-drill-guide/image-9a1f45dd-b174-4e1d-b106-ceff0c6cf88b-1600x900-480d06fef245.webp)

## 03. Draw the V-groove profile

Open a YZ sketch and use Line to draw a closed triangle. In Select mode, enable Vertex Shaping. Right-click the vertices and set their sketch-local coordinates to (−8, −2), (8, −2), and (0, 6) mm. The first coordinate follows world Y and the second follows world Z. The profile extends below the base, so its intersection with Z0 gives a 12 mm opening and a 90° groove with a 6 mm depth.

![A closed triangular YZ sketch with the exact V-groove coordinates](https://assets.reactor3d.xyz/tutorials-page/articles/3d-printed-drill-guide/image-6cb35d2e-3f2f-4461-8336-4d9baa9fe40e-1600x900-0eaa13d1e1fc.webp)

## 04. Extrude and center the cutter

Select the triangular loop and extrude it 64 mm as a new part. Rename it V Groove Cutter. With rotation at zero, set its position to X−32, Y0, Z0. It spans X−32 to X+32, reaching 2 mm beyond each end of the body.

![The centered 64 mm cutter spans both ends of the body](https://assets.reactor3d.xyz/tutorials-page/articles/3d-printed-drill-guide/image-2ac7abd5-49d6-4b73-8fe2-e1d3e200778f-1600x900-ac4eb2bf2175.webp)

## 05. Cut the groove through the body

In Cut, set Drill Guide Body as the target and V Groove Cutter as the tool. Keep source parts off and confirm. Check underneath for an uninterrupted groove and a flat support band along each side.

![Cut preview with the body as target and the prism as tool](https://assets.reactor3d.xyz/tutorials-page/articles/3d-printed-drill-guide/image-f27d86c1-d5a2-474f-be01-03e8de862d2b-1600x900-7fe5f7205c75.webp)

## 06. Create the stepped sleeve seat

Select the top planar face and use Hole → Simple hole → Counterbore. Set head diameter to 10.2 mm, head depth to 16 mm, hole diameter to 6.5 mm and through-cut depth to 30 mm. In Advanced settings, enter part X0 and Y0 independently and confirm that the preview is centered on Z24. The seat shoulder is at Z8, 2 mm above the V apex. The smaller hole exits into the groove. A nominal Ø10 mm sleeve has 0.2 mm diametral clearance, or 0.1 mm radial clearance.

![The centered counterbore with a 10.2 mm seat and a 6.5 mm exit](https://assets.reactor3d.xyz/tutorials-page/articles/3d-printed-drill-guide/image-fac7372e-1493-4641-87d4-509c85474387-1600x900-556ebc91c3ce.webp)

## 07. Model the sleeve as a separate part

Create a cylinder named Guide Bushing 6 mm, with a 5 mm radius and a 16 mm height. Set its temporary world position to X45, Y0, Z8 and leave rotation at zero. The cylinder represents a purchased metal sleeve.

![The separate nominal sleeve at its temporary working position](https://assets.reactor3d.xyz/tutorials-page/articles/3d-printed-drill-guide/image-32ec8848-2a75-48a1-b7c2-0d5f029ba072-1600x900-b284b0c0424b.webp)

## 08. Bore the sleeve and chamfer the entrance

In Hole, enable Snap to center and select the sleeve’s top circular face. Choose Simple hole → Chamfer. Enter a 6 mm diameter, 20 mm depth, 6.8 mm chamfer diameter and 90° included angle. The cut passes through the 16 mm sleeve and opens the entrance by 0.4 mm radially.

![A 6 mm sleeve bore with a 6.8 mm chamfer entrance](https://assets.reactor3d.xyz/tutorials-page/articles/3d-printed-drill-guide/image-474d5fa9-a12d-49eb-99b8-aae8b532cfbd-1600x900-e2077136ce06.webp)

## 09. Seat the sleeve and inspect the bore

Move Guide Bushing 6 mm to X0, Y0, Z8 with zero rotation. Its bottom should rest at the Z8 shoulder and its top should meet the Z24 top plane. Keep the body and sleeve as distinct parts. Look down the bore, then orbit underneath to verify that the exit opens into the V-groove.

![The sleeve seated with its top flush at Z24](https://assets.reactor3d.xyz/tutorials-page/articles/3d-printed-drill-guide/image-6cf4e4dd-af8c-4c23-89db-708fe92c606b-1600x900-33fde37cfcf1.webp)

## What to check on the finished model

If the groove stops early, check the 64 mm cutter and its X−32 position. If the wrong body disappears, recheck the target/tool order. If the sleeve protrudes, check its 16 mm height and Z8 base position. If the seat is off center, recheck the two coordinate fields in Advanced settings.

## CAD fit and printed fit

The dimensions are CAD targets. Measure the real metal sleeve and print a small seat test piece before committing to the full body. Adjust the seat diameter separately to preserve the other dimensions and tool axis. Printed fit, sleeve retention and drilling accuracy still need practical testing before use.

## Practice model and source

[Download the two-part STEP model](v-groove-drill-guide.step). The body and sleeve are separate solids. [Upstream STEP resource](https://api.reactor3d.xyz/tutorials/en/3d-printed-drill-guide/resources/4fdb2de6-37f4-4f5d-9a1a-2cf8130ce50b/download).

Original tutorial by the Reactor 3D Team: [Model a Drill Guide for 3D Printing](https://reactor3d.xyz/en/tutorials/3d-printed-drill-guide).

More CAD practice at the [Reactor 3D homepage](https://reactor3d.xyz/).
