# Downstream Task-agnostic Transferable Attacks on Language-Image Pre-training Models

The project page for the paper:

Lv, Yiqiang, et al. "Downstream Task-agnostic Transferable Attacks on Language-Image Pre-training Models." 2023 IEEE International Conference on Multimedia and Expo (ICME). IEEE, 2023. [[PDF page](https://ieeexplore.ieee.org/abstract/document/10219910)]





#### Target model weight can be downloaded from: [[address](https://pan.baidu.com/s/1fQy9Xms-iS0qeQezzz46Qg?pwd=0000)]

Image classification (wise_ft_alpha=0.700.pt) (Tuned by myself, cite: [[Wise-FT](https://github.com/mlfoundations/wise-ft/tree/master)])<br>

Video recognition (vit-32-8f.pt)  (model and config from, cite: [[ActionCLIP](https://github.com/sallymmx/ActionCLIP)])<br>

Video-text retrieval (pytorch_model.bin.2) (model and config from, cite: [[ClIP2Video](https://github.com/CryhanFang/CLIP2Video)])<br>



#### For generating adv examples (todo: some absolute path in code should be exchanged):

Image classification: (e.g.) <br>

```text
python attack.py --downstream_task ImagenetCLS --generate_model_name 'ViT-B/16' --attack 'GLA' \
		 --use_adam 1 --clean_datapath 'image_path' \
                 --results_path 'path' --batch_size 192 \
		 --cpu_num 8  --patch_size 16 --steps 60  --mid_layer 4
```



Video recognition: (e.g.)<br>

```
python attack.py --generate_model_name 'ViT-B/16' --attack 'GLA'  --mid_layer 4 --patch_size 16 --use_adam 1  --steps 60
```

Video-text retrieval: (e.g.)<br>

```text
python attack.py --downstream_task CLIP2Video --generate_model_name 'ViT-B/16' --attack 'GLA' \
                 --use_adam 1  --clean_datapath 'clean_correct_path' \
		 --results_path 'result_path' --batch_size 18 \
		 --overwrite 1 --cpu_num 8  --patch_size 16 --steps 60  --mid_layer 4
```



​        
