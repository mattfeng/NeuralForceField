# Package structure

- `nff`
  - `nff.nn`
    - `nff.nn.modules`. layer definitions for each model (e.g. SchNet) in `nff.nn.models`
    - `nff.nn.models`
  - `nff.train`
    - `nff.train.builders`
      - `model.py`. contains comprehensive lists of network model parameters for initialization
  - `nff.data`
    - `crystals.py`
      - `get_crystal_graph(crystal, cutoff)`
    - `dataset.py`
      - provides information on `props` dictionary passed into models
      - `props` is a dictionary of lists, where each element in the list corresponds to one example in the training set
        - e.g. `props["nxyz"][0]` returns the atomic numbers and coordinates for the first training example in the `Dataset`
      - if `lattice` key provided in `props` dictionary, the `Dataset` class computes a periodic neighbor list (`Dataset.generate_neighbor_list`).