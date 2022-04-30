# PokeTypeGAN
Generating new Pokemon with specified type combinations, based on ACGAN + DiffAugment + D2DCE.

![index](https://tva1.sinaimg.cn/large/e6c9d24egy1h1s3hp1lfuj20p60cxtaq.jpg)

## Dataset

The used dataset can be downloaded from: [pokemon_images.zip](https://drive.google.com/file/d/1ZNBuTgFPD007Yvqq1GwrfwccFYdnLP2M/view?usp=sharing), with total 10,437 Pokemon sprites (half of them are shiny variants) in 96x96 resolution collected from 898 Pokemon in different games. Below are the collected images of Bulbaraur:

| Gen3 E                                                       | Gen3 E (Frame 2)                                             | Gen3 FL                                                      | Gen4 DP                                                      |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| ![1-gen3_e](https://tva1.sinaimg.cn/large/e6c9d24egy1h1s44084dzj202o02ojr5.jpg)![1-gen3_e](https://tva1.sinaimg.cn/large/e6c9d24egy1h1s443w5bhj202o02oq2p.jpg) | ![1-gen3_e-frame2](https://tva1.sinaimg.cn/large/e6c9d24egy1h1s448n6rnj202o02oq2p.jpg)![1-gen3_e-frame2](https://tva1.sinaimg.cn/large/e6c9d24egy1h1s449yt3qj202o02ot8h.jpg) | ![1-gen3_fl](https://tva1.sinaimg.cn/large/e6c9d24egy1h1s44ddqeij202o02ojr5.jpg)![1-gen3_fl](https://tva1.sinaimg.cn/large/e6c9d24egy1h1s44ivp4hj202o02ot8h.jpg) | ![1-gen4_dp](https://tva1.sinaimg.cn/large/e6c9d24egy1h1s44n23xsj202o02owe9.jpg)![1-gen4_dp](https://tva1.sinaimg.cn/large/e6c9d24egy1h1s44rt84xj202o02o0si.jpg) |

| Gen4 HS                                                      | Gen4 HS (Frame 2)                                            | Gen5                                                         | Gen5 (Back)                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| ![1-gen4_hs](https://tva1.sinaimg.cn/large/e6c9d24egy1h1s44uk1ccj202o02ot8h.jpg)![1-gen4_hs](https://tva1.sinaimg.cn/large/e6c9d24egy1h1s44ypz9tj202o02ot8h.jpg) | ![1-gen4_hs-frame2](https://tva1.sinaimg.cn/large/e6c9d24egy1h1s4511vlyj202o02ot8h.jpg)![1-gen4_hs-frame2](https://tva1.sinaimg.cn/large/e6c9d24egy1h1s455gbezj202o02ot8h.jpg) | ![1-gen5](https://tva1.sinaimg.cn/large/e6c9d24egy1h1s456rn88j202o02oq2p.jpg)![1-gen5](https://tva1.sinaimg.cn/large/e6c9d24egy1h1s45930ibj202o02oq2p.jpg) | ![1-gen5](https://tva1.sinaimg.cn/large/e6c9d24egy1h1s45b1szzj202o02ogld.jpg)![1-gen5](https://tva1.sinaimg.cn/large/e6c9d24egy1h1s45e9ffqj202o02ogld.jpg) |

Labels that may relate to Pokemon’s appearance are extracted from PokeIndex and stored as a CSV file. Below is the sample entry of Bulbasaur:
| **name**  | **pokedex_id** | **type1** | **type2** | **primary_color** | **shape** | **legendary** | **mega_evolution** | **alolan_form** | **galarian_form** | **gigantamax** |
| --------- | -------------- | --------- | --------- | ----------------- | --------- | ------------- | ------------------ | --------------- | ----------------- | -------------- |
| Bulbasaur | 1              | Grass     | Poison    | Green             | Quadruped | FALSE         | FALSE              | FALSE           | FALSE             | FALSE          |

In this repository only the type labels are used. Of course we can also try generating new Pokemon conditioned on other labels.

## Training and Testing

The notebook is self-contained and ran on Google Colab. Just modify those Colab-specific codes and Google Drive specific paths to run locally.

## Sample Generated Images and Model Weights

Sample generated images of all possible (either one or two, in total 171) type combinations are provided in `gen_results/`, and the used model weights is provided in `checkpoints/`. 

For example, let’s create some fire fairies:

<img src="./gen_results/00253k-Fire+Fairy.png" alt="00253k-Fire+Fairy"  />

and some electric ice-mon:

![00253k-Electric+Ice](./gen_results/00253k-Electric+Ice.png)

and some dark bugs (that we programmers hate):

![00253k-Bug+Dark](./gen_results/00253k-Bug+Dark.png)
