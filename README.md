# mrtklib-data

Test and sample datasets for [MRTKLIB](https://github.com/h-shiono/MRTKLIB),
published as **release assets** of this repository. The repository itself holds
no code and no data files; only this README.

You do not need anything from here to build or use MRTKLIB. The datasets are
fetched on demand by MRTKLIB's ctest fixtures and by the quickstart guides:

```bash
cmake --build build --target fetch-test-data   # optional: fetch everything in advance
cd build && ctest                               # fetches what each test needs
```

## Layout

- One release per dataset version, tagged `<dataset>-v<N>`, with one asset
  `<dataset>-v<N>.tar.gz`.
- Releases are immutable: an asset is never changed or replaced. A changed
  dataset is published as `<dataset>-v<N+1>`.
- MRTKLIB pins each dataset by URL and SHA256 in `tests/data/datasets.cmake`;
  provenance (source capture, time window, processing) is documented next to
  the consuming tests in MRTKLIB, under `tests/data/<dataset>/`.

See MRTKLIB issue [#386](https://github.com/h-shiono/MRTKLIB/issues/386) for the design.
