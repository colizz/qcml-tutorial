Models are adapted from https://github.com/hqucms/weaver-core/tree/aff65317a353534ccadb76d8f7e16403690bae4e/weaver/nn/model.

For both `ParticleNet.py` and `ParticleTransformer.py`, the new classes are added (`ParticleNetTaggerMultiGroups` and `ParticleTransformerTaggerMultiGroups`) to adapt for the case where multiple groups of "tokens" are in presence and will undergo separate embeddings.
