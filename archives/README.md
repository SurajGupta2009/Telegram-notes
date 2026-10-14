# Study note archives

Prepared from the six named Google Drive folders on 2026-10-14. Each logical ZIP contains only the PDFs found recursively under its source folder and preserves the original filenames and subfolder paths. Non-PDF files (images, DOCX, TXT, etc.) are intentionally excluded.

PDFs were optimized losslessly with Flate-stream recompression and PDF object streams; an optimized copy was kept only when it was smaller and passed an open/page-count check. No image downsampling or lossy image re-encoding was used. ZIP compression used DEFLATE level 9. Across all 60 PDFs, the result is about 5.4% smaller than the original source bytes.

| Source folder | Logical ZIP | PDFs | Total ZIP bytes | How it is stored here |
|---|---|---:|---:|---|
| Physics Notes | `physics-notes.zip` | 3 | 64,286,840 | Single ZIP |
| Chemistry Notes | `chemistry-notes.zip` | 5 | 43,185,703 | Single ZIP |
| Maths Notes | `maths-notes.zip` | 24 | 346,215,493 | Four parts: `maths-notes.zip.001`–`.004` |
| Class 12 Physics JEE & NEET | `class-12-physics-jee-neet.zip` | 7 | 94,953,760 | Single ZIP |
| Class 11 Physics JEE & NEET | `class-11-physics-jee-neet.zip` | 7 | 21,586,871 | Single ZIP |
| Competishun YT Lecture Notes | `competishun-yt-lecture-notes.zip` | 14 | 407,607,495 | Five parts: `competishun-yt-lecture-notes.zip.001`–`.005` |
| **Total** |  | **60** | **977,836,162** |  |

GitHub rejects individual regular Git files at 100 MB, so the Maths and Competishun ZIPs are stored as 90,000,000-byte chunks. Clone this repository, then reassemble, verify, and extract them from the repository root:

```sh
cat archives/maths-notes.zip.0* > maths-notes.zip
cat archives/competishun-yt-lecture-notes.zip.0* > competishun-yt-lecture-notes.zip
sha256sum -c archives/SHA256SUMS
unzip maths-notes.zip
unzip competishun-yt-lecture-notes.zip
```

The four single-file archives can be extracted directly, for example:

```sh
unzip archives/physics-notes.zip
```

All six logical ZIPs passed CRC tests. The archived PDFs were hash-checked against their optimized source files; the split archives were reassembled and verified before publication. `SHA256SUMS` contains checksums for all six completed ZIPs.
