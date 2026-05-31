# MEX-LIP-READ

**MEX-LIP-READ** is a visual speech recognition dataset for **Mexican Spanish**, designed to support lip reading research across a broad set of phonetic units. While most existing lip reading datasets focus on English, this dataset addresses the lack of resources for Spanish by covering **vowels**, **consonant-vowel syllables**, and **consonant clusters** (*sinfones*).

The dataset was recorded by **24 participants** and contains **11,009 labeled motion sequences**, each represented as 18 consecutive frames extracted from video. Sequences are organized into **155 syllabic classes** across three phonetic categories, totaling over **198,000 images** at a uniform resolution of 128×128 pixels. The dataset is intended for tasks such as syllable-level classification, sequence modeling, and the development of lip reading systems for Spanish speakers.

![Examples of frames extracion from a clip.](img/Frame%20Extraction.jpg)

---

## Overview

MEX-LIP-READ was collected from **24 participants** and covers three phonetic categories of Mexican Spanish: vowels, consonants (consonant-vowel syllables), and consonant clusters. The dataset provides both raw video recordings and pre-extracted frame sequences ready for model training.

| Subset | Class N. | Subclass N. | Clips N. | Frames N. | Storage Size |
|---|---|---|---|---|---|
| Vowels | 5 | 5 | 349 | 6,282 | 27.5 MB |
| Consonants | 17 | 85 | 6,020 | 108,360 | 703 MB |
| Consonant Clusters | 13 | 65 | 4,640 | 83,520 | 535 MB |
| **Total** | **35** | **155** | **11,009** | **198,162** | **1,265.5 MB (1.27 GB)** |

---

## Repository Structure

```
Dataset/
├── Vowels/                  # Vowel syllables
│   ├── A/
│   ├── E/
│   ├── I/
│   ├── O/
│   └── U/
├── Consonants/              # Consonant-vowel syllables
│   ├── B/
│   │   ├── BA/
│   │   ├── BE/
│   │   ├── BI/
│   │   ├── BO/
│   │   └── BU/
│   └── ... (C, CH, D, F, G, GN, J, K, L, M, N, P, R, S, T, Y)
└── Consontant/                 # Consonant cluster syllables
    ├── BL/
    │   ├── BLA/
    │   ├── BLE/
    │   ├── BLI/
    │   ├── BLO/
    │   └── BLU/
    └── ... (BR, CL, CR, DR, FL, FR, GL, GR, PL, PR, TL, TR)
```
![Dataset structure](img/Frames%20Dataset%20Diagram.png)
---

## Phonetic Categories

### Vowels

Five classes corresponding to the Spanish vowels: **A, E, I, O, U**.

Each sequence folder is named with the pattern `<ParticipantID>_<vowel>_<repetition>` (e.g., `P10_a_1`).

![Vowels structure](img/Vowels%20-%20Diagram.png)

### Consonants

17 consonants combined with each of the 5 vowels, yielding **85 classes**:

| Consonants | |
|---|---|
| B, C, CH, D, F | G, GN, J, K, L |
| M, N, P, R, S | T, Y | |

Example class names: `BA`, `BE`, `BI`, `BO`, `BU`, `CHA`, `CHE`, ...

![Consonant structure](img/Consonants%20-%20Diagram.png)
### Consonant Clusters

13 two-consonant clusters combined with each of the 5 vowels, yielding **65 classes**:

`BL, BR, CL, CR, DR, FL, FR, GL, GR, PL, PR, TL, TR`

Example class names: `BLA`, `BLE`, `BRI`, `CRO`, `TRU`, ...

![Consonant Clusters structure](img/Sinfones%20-%20Diagram.png)
---

## Frame Sequences

Each motion sequence is stored as a subfolder inside its class directory, containing **18 frames** in `.jpg` format named `1.jpg` through `18.jpg`.

```
Fotogramas/Vocales/A/P10_a_1/
├── 1.jpg
├── 2.jpg
├── ...
└── 18.jpg
```

### Image Properties

| Property | Value |
|---|---|
| Format | JPEG (`.jpg`) |
| Resolution | 128 × 128 px |
| Color space | RGB |
| Bit depth | 8 bits per channel |
| Approx. file size | ~5–7 KB per frame |

All frames are cropped and resized to a fixed **128×128 pixel** resolution, centered on the speaker's mouth region. The consistent resolution and color space make the dataset directly compatible with standard CNN-based and sequence-based deep learning pipelines without additional preprocessing.

---

## Participants

The dataset was recorded by **24 participants**, identified as `P1` through `P24`. Raw video recordings per participant are available in the `Videos/` folder.

---

## Use Cases

- Visual speech recognition (lip reading) for Mexican Spanish
- Syllable-level classification
- Sequence modeling (RNN, LSTM, Transformer)
- Data augmentation research for low-resource languages

---

## Citation

If you use this dataset in your research, please cite:

```bibtex
@dataset{mexlipread2024,
  title   = {MEX-LIP-READ: A Mexican Spanish Lip Reading Dataset},
  year    = {2024},
}
```

---

## Dataset Access

### Preview

A subset of the dataset is available directly in the `Dataset/` folder of this repository. It includes a sample of sequences across all three phonetic categories and can be used to explore the structure and format before requesting the full dataset.

### Full Dataset

The complete dataset is not publicly hosted due to its size. To request access, send an email to one of the following addresses with a brief description of your intended use:

- `ejec19@example.com`

**Subject:** `[MEX-LIP-READ] Dataset Access Request`

**Body should include:**
- Your name and institutional affiliation
- A brief description of your research or project
- Intended use of the dataset

We will respond with a download link or further instructions.

---

## License

*License information pending.*
