# ONOT-TONO Printed

ONOT–TONO **256** print corpus for ICAO face-quality work.

- **synthetic/** — simulated print techniques (5 techs)
- **real/** — physically printed and scanned (toner + inkjet)

Protocol: ONOT-TONO 256 (`bona256` + ICAO attack axes from the 256icao pairing).

## Layout

```
repo_onot_tono/
  synthetic/
    onot/<tech>/                 # 256 bona (flat)
    tono/<tech>/<axis>/          # ICAO attacks (cap, sun, sm, ce, la_1, la_2, tq)
  real/
    onot/toner|inkjet/           # 256 bona each
    tono/toner/<axis>/           # all ICAO axes (256 filter)
    tono/inkjet/<axis>/          # only cap + tq filled; other axes empty
  examples/
```

Techs: `toner`, `inkjet`, `dye`, `laser_engraved`, `thermal_transfer`.

Images are **full copies** (not symlinks), ready to `git add` / push.

### Real inkjet TONO

Only **hat (`cap`)** and **pose (`tq`)** are reliable. Other inkjet attack
folders are present but empty.

## Examples

One ONOT identity across **five synthetic** print techniques:

![Synthetic 5 techs](examples/synth_5tech.png)

Same identity across **two real** print+scan techniques:

![Real toner and inkjet](examples/real_2tech.png)

Identity file: `examples/identity.txt`.

## Counts (256 protocol)

| split | content | n |
| --- | --- | ---: |
| synthetic / onot | bona × 5 techs | 256 × 5 |
| synthetic / tono | ICAO attacks × 5 techs | 1707 × 5 |
| real / onot | bona × 2 techs | 256 × 2 |
| real / tono / toner | ICAO attacks | 1707 |
| real / tono / inkjet | cap + tq only | 281 + 50 |

## References

This repo reuses images from the public **ONOT** and **TONO** datasets
(MI@BioLab, University of Bologna). Please cite the original papers if you use them.

### ONOT

- Project page: https://miatbiolab.csr.unibo.it/icao-synthetic-dataset/
- IEEE FG 2024: https://doi.org/10.1109/fg59268.2024.10581986
- arXiv: https://arxiv.org/abs/2404.11236

```bibtex
@inproceedings{di2024onot,
  title     = {{ONOT}: a High-Quality {ICAO}-compliant Synthetic Mugshot Dataset},
  author    = {Di Domenico, Nicol{\`o} and Borghi, Guido and Franco, Annalisa and Maltoni, Davide},
  booktitle = {IEEE International Conference on Automatic Face and Gesture Recognition (FG)},
  year      = {2024},
  doi       = {10.1109/FG59268.2024.10581986}
}
```

### TONO

- Project page: https://miatbiolab.csr.unibo.it/tono-synthetic-dataset/
- ECCV Workshops 2024: https://doi.org/10.1007/978-3-031-91907-7_1

```bibtex
@inproceedings{borghi2024tono,
  title     = {{TONO}: a Synthetic Dataset for Face Image Compliance to {ISO}/{ICAO} Standard},
  author    = {Borghi, Guido and Franco, Annalisa and Di Domenico, Nicol{\`o} and Maltoni, Davide},
  booktitle = {European Conference on Computer Vision Workshops (ECCVW)},
  year      = {2024},
  doi       = {10.1007/978-3-031-91907-7_1}
}
```

## License note

ONOT and TONO are released under **CC BY-NC 4.0** by their authors.
The print imitations and real print+scan material in this folder inherit
those terms for the underlying faces; cite ONOT/TONO as above.
