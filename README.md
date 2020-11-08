# RL-based-Graph2Seq-for-NQG
Code & data accompanying the ICLR 2020 paper ["Reinforcement Learning Based Graph-to-Sequence Model for Natural Question Generation"](https://arxiv.org/abs/1908.04942).

## Get started


### Prerequisites
This code is written in python 3. You will need to install a few python packages in order to run the code.
We recommend you to use `virtualenv` to manage your python packages and environments.
Please take the following steps to create a python virtual environment.

* If you have not installed `virtualenv`, install it with ```pip install virtualenv```.
* Create a virtual environment with ```virtualenv venv```.
* Activate the virtual environment with `source venv/bin/activate`.
* Install the package requirements with `pip install -r requirements.txt`.



### Run the model

* Download the preprocessed data from [squad-split1](https://1drv.ms/u/s!AjiSpuwVTt09gUda3WWPURcCfubF?e=eFhgUQ) and [squad-split2](https://1drv.ms/u/s!AjiSpuwVTt09gUiTsPKFj4hy4RzU?e=bhk65z). And put the data under the root directory. So the file hierarchy will be like: `data/squad-split1` and `data/squad-split2`. 


* Run the model

    ```
    python main.py -config config/squad_split1/graph2seq_static_bert_finetune_word_70k_0.4_bs_60.yml
    ```
  	Note that you can specify the output path by modifying `out_dir` in a config file. 
  	If you want to finetune a pretrained model, you can specify the path to the pretrained model by modifying `pretrained` and you need to set `out_dir ` to null.
  	If you just want to load a pretrained model and evaluate it on a test set, you need to set both `trainset` and `devset` to null.
  	
    

* Finetune the model using RL

    ```
    python main.py -config config/squad_split1/rl_graph2seq_static_bert_finetune_word_70k_0.4_bs_60.yml
    ```



## Reference

If you found this code useful, please consider citing the following paper:

Yu Chen, Lingfei Wu and Mohammed J. Zaki. **"Reinforcement Learning Based Graph-to-Sequence Model for Natural Question Generation."** In *Proceedings of the 8th International Conference on Learning Representations (ICLR 2020), Addis Ababa, Ethiopia, Apr. 26-30, 2020.*


	@inproceedings{chen2019reinforcement,
    author    = {Chen, Yu and Wu, Lingfei and Zaki, Mohammed J.},
    title     = {Reinforcement Learning Based Graph-to-Sequence Model for Natural Question Generation},
    booktitle = {Proceedings of the 8th International Conference on Learning Representations},
    month = {Apr. 26-30,},
    year      = {2020}}
