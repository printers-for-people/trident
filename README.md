# Formbot Trident R1 kit description

## What is this?

We attempt to catalogue and describe the features (good and bad) of the [Formbot
Trident R1 kit][kit]. We also suggest fixes and improvements for its issues, and
provide references to helpful additional materials. Our goal in writing this is
to help advise future buyers, and help them avoid gotchas or bad choices,
especially if they are first-time builders.

## Disclaimers

* We built the 250mm kit; larger ones might require different components.
* We decided to replace the Stealthburner with the Dragonburner. Thus, no
  components related to the Stealthburner were evaluated.
* We are writing this guide as we go, so there might be issues we haven't
  covered, or didn't ever hit. Let us know if we missed something!

## Issues

These are issues we have found with both the kit, and the Voron Trident in
general, during our build.

### Stock idlers are garbage

This is a problem with Voron Design, rather than the Formbot kit. Essentially,
the stock A and B idlers are badly-designed and full of problems:

* Their print orientation means that belt tension applies force that tries to
  pull layers apart. This can lead to [breakages][idler-break].
* The bearing stack is held in place with a temporary M5 screw, which must then
  be removed before the idler proper can be slid in place. This is error-prone,
  as the stack can easily collapse before it can be stabilized with another
  screw, making the build frustrating and tedious.
* It uses captive M5 nuts, which have a tendency to fall out while building,
  making the assembly process even more frustrating. Furthermore, this kind of
  design is wholly not necessary, as M5 heatset inserts exist.

The correct solution is to not use the stock A and B idlers, instead using
[BFIs][bfi]. The default configuration of BFIs is asymmetric, but if you prefer
a symmetric look, a [modded version][symmetric-bfi] exists. You will need some
additional components if you want to build the BFIs:

* 4 x [M5x40 SHCS][liya-shcs]
* 4 x [M5 hex nuts][liya-hex-nut]
* 2 x [5mm diameter pin, 18mm long][liya-pin]

You will also need the original bearings and shims from the kit. You want to 
print the following parts (for default BFIs):

* [`BFI-VT_Housing_x2.stl`](https://github.com/clee/VoronBFI/blob/main/STLs/BFI-VT_Housing_x2.stl)
* [`[a]_BFI-VT_Carrier_x2.stl`](https://github.com/clee/VoronBFI/blob/main/STLs/%5Ba%5D_BFI-VT_Carrier_x2.stl)
* [`[a]_BFI-VT_Front_x3.stl`](https://github.com/clee/VoronBFI/blob/main/STLs/%5Ba%5D_BFI-VT_Front_x2.stl)

TODO: Add the exact parts needed for symmetrical BFI as well.

These replace all parts in the `Front_Idlers` directory. Although there are no
current assembly instructions, [this video (at the given
timestamp)][bfi-assembly] shows the process.

### Low-quality T-nuts

The T-nuts provided by the kit (both M3 and M5) are of low quality. They are
difficult, if not impossible, to load into an already-assembled frame, and are
hard to remove. Additionally, many of them are faulty, either being too stiff
(as their retaining ball won't move properly) or too loose (because the
retaining ball is missing), or having issues with bad hole drillout.

![An M5 T-nut, viewed from the top. Its screw hole is very badly drilled, with a
lot of flash, causing the hole diameter to be much smaller than it's supposed to
be.](./img/bad-m5.jpg)

![A collection of T-nuts, both M3 and M5, in a blue small parts tray. Some have
visibly bad drilling on their holes, some have lost their retaining balls. These
is a stray spring visible.](./img/many-bad-m5s.jpg)

You have several options for a solution. The least expensive, but most annoying,
is to preload all the T-nuts prior to assembling the frame. There is a [video
source on how to do this][preload-tnuts-video], but this is designed for the LDO
kit, which uses nut bars. You can replace any use of nut bars with eight M3
T-nuts, arranged in a four-and-four mirror setup. After this, you can assemble
the frame as per the build manual.

TODO: Image from manual page of how this should look.

TODO: We should just describe the preload in words.

The second option is to buy better T-nuts. If the option is available to you,
[Misumi ones][misumi-t-nut] are the best option, but they can be prohibitively
expensive, especially if you live outside of the EU or North America. You can
find cheaper ones, but your mileage may vary. We usually find
[Liya][liya-t-nut] fasteners to be of good quality, but as we haven't tested
these specific T-nuts, buy and use at your own risk. By the BOM (for a 250mm
Trident), you want at least 70 M5 T-nuts, and 90 M3 T-nuts, but more would
definitely be better.

A third option (technically outside of the spec) is to replace T-nuts with
hammer nuts. While these have some downsides, both RatRig and VzBot consider
hammer nuts sufficient for the same purposes that the Trident build uses 
T-nuts. However, once again, we haven't tested this, so proceed with care if you
choose to do this. As previously, you would want 70 M5 nuts and 90 M3 nuts, but
as they're quite useful for attaching things to extrusions, it'd be better to
get more.

[kit]: https://www.formbot3d.com/products/voron-trident-corexy-3d-printer-kit-with-premade-wiring-harness
[preload-tnuts-video]: https://www.youtube.com/watch?app=desktop&v=hpkN9NHoKiY
[misumi-t-nut]: https://fermio.xyz/misumi-europa-gmbh/misumi-t-slot-nut-hntaj5-3-6-mm-slot-m3-thread
[liya-t-nut]: https://www.aliexpress.com/item/4000577562903.html
[idler-break]: https://raw.githubusercontent.com/clee/VoronBFI/main/images/cracked_stock.jpg
[bfi]: https://github.com/clee/VoronBFI
[symmetric-bfi]: https://github.com/clee/VoronBFI/tree/main/usermods/Tetsu/Symetrical%20BFI
[liya-shcs]: https://www.aliexpress.com/item/32542380485.html
[liya-hex-nut]: https://www.aliexpress.com/item/32868247852.html
[liya-pin]: https://www.aliexpress.com/item/1005001502867783.html
[bfi-assembly]: https://www.youtube.com/watch?v=XtfESO4ALw8&t=970s
