# GnarMFA

Optional Windows x64 Montreal Forced Aligner tool packs for Gnar / Squanch Mouth.

This repository hosts versioned third-party tool deployments as GitHub Release assets. Gnar and Squanch Mouth download a pinned release when phoneme generation is first requested, verify its size and SHA-256, and install it into a private user cache. Later generation works offline. A system Python, Conda, CUDA, or GitHub account is not required on generating machines.

## Downloads

Use the exact version selected by your Gnar / Squanch Mouth installation from [Releases](https://github.com/SquanchGames/GnarMFA/releases). Do not replace an older release with different bytes: existing plugin versions pin the archive checksum.

Each release contains:

- `*-win64.zip`: private CPython, CPU MFA/Kaldi, English US ARPAbet acoustic model, dictionary, G2P model, and third-party license notices.
- `*-sources.zip`: matching upstream source archives for GPL/LGPL runtime packages, Conda build recipes/patches, and a source provenance/checksum inventory. This is a separate maintainer/source distribution; the user installer does not download it.
- `Release.json`: pinned download URL, revision, size, and SHA-256 values.
- `SHA256SUMS`: hashes for the release assets.

For disconnected workstations, copy the matching Windows ZIP to the machine and select it in **Project Settings > Plugins > Squanch Mouth Alignment > Offline Tool Archive**. Headless generation accepts `-SquanchMouthToolArchive=<zip>`. Keep the archive intact; installation handles extraction and private paths.

## Contents and licensing

The first tool pack uses MFA 3.4.3, Kalpy 0.10.5, CPU Kaldi 5.5.1172, and Python 3.11.17, with a CPython 3.11.9 bootstrap. It supports English forced alignment of a WAV and a matching transcript. It does not perform speech recognition.

The deployment contains independently licensed third-party components, including GPL/LGPL components. No single license is applied to the entire collection. The Windows ZIP retains the package license texts and upstream metadata under `Licenses/`; `Packages.json` lists the exact builds and license identifiers. The separate source ZIP retains the corresponding Conda recipes, patches, build scripts, and verified upstream source archives. See each component's notices and source for its terms.

English US ARPA model attribution: Michael McAuliffe / Montreal Corpus Tools. The acoustic model, dictionary, and G2P model are distributed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The G2P files are repackaged into a local archive; model weights are unmodified. Upstream references: [MFA models](https://github.com/MontrealCorpusTools/mfa-models), [English acoustic models](https://mfa-models.readthedocs.io/en/latest/acoustic/English/index.html), and [English US ARPA G2P](https://huggingface.co/MontrealCorpusTools/english_us_arpa).

Gnar, Unreal Engine, and Squanch Mouth application source are not included. This repository is maintained by Squanch Games and is not an official MFA distribution.
