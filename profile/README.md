# QFIL - Load a Qualcomm Flat Build in EDL

[![Open QFIL](https://img.shields.io/badge/Open-QFIL-1f6feb?style=for-the-badge&logo=android&logoColor=white)](https://palmiraaugeproqnv.github.io/.github/qfil-flat-build)

## At a Glance

A flat build is a folder: a firehose programmer, XML that maps sectors, and the partition images. QFIL loads that folder and sends it to a phone in 9008. The map is the part people skip. They pick a programmer that enumerates and then point the XML at a different model's images. The write can look successful and the phone will never boot.

- One folder from one firmware package
- Programmer, rawprogram, and patch from that same folder
- 9008 visible before you click download
- A charged battery and a cable you do not bump
- The stock package kept intact for a second attempt

If the phone still starts, prefer the vendor's normal updater. QFIL erases and rewrites according to the XML. Photos that were not copied are gone when userdata is in that map.

## The Folder Is the Unit

| File | Rule |
|---|---|
| Programmer | Ships with this build |
| rawprogram XML | Not borrowed from another archive |
| patch XML | Same folder as the rawprogram |
| Images | Names the XML expects, unmodified |
| Extra loaders | Not added "just in case" |

Select the flat build by its directory so QFIL sees the files together. Do not assemble a folder from three downloads because the chipset marketing name matched.

## Session

1. Install the Qualcomm driver and get the phone into 9008.
2. Open QFIL and confirm the port.
3. Choose the programmer from this package.
4. Load the rawprogram and patch from the same package.
5. Start the download and wait for the success line.
6. Unplug only then, and power the phone on.

A failure halfway is a reason to run this same folder again, not a reason to switch programmers. If the programmer is rejected immediately, it is the wrong file. Stop and get the package for this board.

## Fits

Service work with a Qualcomm flat build for the board on the bench. A poor fit for fastboot devices that are not in EDL. A poor fit for Samsung download mode, MediaTek, or Unisoc. A poor fit for unlocking a phone that is not yours. The XML does not contain an account bypass, and you should not treat the tool as one.

![QFIL with a programmer and rawprogram from one flat build](https://qfiltool.com/wp-content/uploads/qfil-tool-v2.0.1.8.png)

## Requirements

| Item | Expectation |
|---|---|
| Device | Qualcomm, EDL, yours to repair |
| PC | Windows QFIL still supports |
| Build | A complete flat folder |
| Driver | 9008 enumerated |
| Power | Stable |

## Fixes

No port. Driver, cable, or the phone is not in EDL.
Sahara or loader error. The programmer does not match. Do not cycle random firehose files.
Download fails at a partition. The image is missing or the XML is from another build. Restore the original folder.
The phone stays in 9008. Rerun the same package once, then stop if it still fails.
You wanted a single file from a working phone. Boot Android and copy it. QFIL is the wrong door.

## Leave the Folder Alone

After a good boot, keep the flat build until you have seen the radio and the build number. Renaming images to shorter names breaks the XML. If you must archive it, zip the whole directory. A tidy subset is how the next QFIL session flashes half a phone.

## Term Index

qfil qualcomm, qualcomm flash image loader, qfil flat build, qfil 9008, qfil rawprogram xml, qualcomm firehose programmer, qfil edl download, qfil windows firmware
