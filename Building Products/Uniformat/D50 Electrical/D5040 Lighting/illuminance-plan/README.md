# Illuminance plan

The two main lighting requirements are:

 1. No artificial light spillage measured 10ft beyond the property
    boundary should be >=0.5fc.
 2. The minimum illuminance across the driveways should be >=0.125fc.
 3. The average illuminance across the driveways should be maximum <=1fc.
 4. The minimum illuminance across the rest should be >=0.2fc.
 5. The average illuminance across the rest should be maximum <=1.5fc.
 6. All luminaires emitting >1000L initially should be full cutoff.

The existing wall mounted entry lights are approximated with [this
product](http://www.cooperindustries.com/content/public/en/lighting/products/outdoor_wall_mount_lighting/_940090.html).
The existing wall mounted direction light at the bottom is approximated with
[this
product](http://www.cooperindustries.com/content/public/en/lighting/products/outdoor_wall_mount_lighting/_187313.html).
The existing high-level facade mounted light is approximated with [this
product](http://www.cooperindustries.com/content/public/en/lighting/products/post_top_lighting/_125641.html).

None of the existing wall lights are relied upon for satisfying the
requirements and so strict simulation is not necessary.

The [NAV Navion
LED](http://www.cooperindustries.com/content/public/en/lighting/products/area_site_lighting/_808353.html)
is specified for the parking light poles. Parking lights are positioned just
under 21' in the air.  The [WKP Wal-Pak Full
Cut-Off](http://www.cooperindustries.com/content/public/en/lighting/products/outdoor_wall_mount_lighting/_183726.html)
is specified for the proposed wall mounted lights.

## How to run

```
$ rad scene.rif
$ ximage scene_v1.hdr # View results
$ falsecolor -ip scene_v1.hdr -cl -l fc -s 3 -m 16.629505759940542 > false.hdr # This scale value provides good isolux contours for validating requirements
$ ximage false.hdr # see contours to verify requirement 1
$ pcomb -o -s 0.0929 scene_v1.hdr > scene_v1_fc.hdr # Convert to fc unit
$ ximage scene_v1_fc.hdr # use `l` to verify requirement 2
```

The source file `scene.blend` provides the `scene.obj` export.
