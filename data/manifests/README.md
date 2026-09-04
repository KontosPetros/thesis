# Split manifests

The final ConvNeXtBase result archive identifies `zoolake_paper_split_deduplicated_semantic.csv` as its immutable manifest. Its SHA-256 is `84ca050319a314f1fbf532f553c1a557763b73a09b2e0f0692d2d6c8182706ad`. The manifest itself is not yet public and is therefore not committed here.

The public ConvNeXt audit reports 12,558 train rows, 2,691 validation rows, and 2,691 test rows, with no filename overlap across splits. The hash is distinct from the common-protocol root manifest `zoolake_clean_split_manifest.csv` even though the split sizes match.
