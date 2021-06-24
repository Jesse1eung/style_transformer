# Style Transformer: Unpaired Text Style Transfer without Disentangled Latent Representation

This folder contains the code for the paper [《Style Transformer: Unpaired Text Style Transfer without Disentangled Latent Representation》](https://arxiv.org/abs/1905.05621)



1. Requirements 
    - pytorch >= 0.4.0
    - torchtext >= 0.4.0
    - nltk
    - fasttext == 0.8.3
    - kenlm
2. nltk
    - Run the following command to download (or double-check) nltk tokenizer dependency:
    ```
    python -c "import nltk; nltk.download('punkt')"
    ```
3. LM for evaluator
    - download from [ppl_yelp.bin](https://drive.google.com/open?id=1pklyWxzNPPxnKNy_TmA8h_tmGmiZttPN)
    - put `ppl_yelp.binary` in the folder `evaluator`



## Usage

The hyperparameters for the Style Transformer can be found in ''main.py''.

The most of them are listed below:

```
    data_path : the path of the datasets
    log_dir : where to save the logging info
    save_path = where to save the checkpoing
    
    discriminator_method : the type of discriminator ('Multi' or 'Cond')
    min_freq : the minimun frequency for building vocabulary
    max_length : the maximun sentence length 
    embed_size : the dimention of the token embedding
    d_model : the dimention of Transformer d_model parameter
    h : the number of Transformer attention head
    num_layers : the number of Transformer layer
    batch_size : the training batch size
    lr_F : the learning rate for the Style Transformer
    lr_D : the learning rate for the discriminator
    L2 : the L2 norm regularization factor
    iter_D : the number of the discriminator update step pre training interation
    iter_F : the number of the Style Transformer update step pre training interation
    dropout : the dropout factor for the whole model

    log_steps : the number of steps to log model info
    eval_steps : the number of steps to evaluate model info

    slf_factor : the weight for self reconstruction loss
    cyc_factor : the weight for cycle reconstruction loss
    adv_factor : the weight for style controlling loss
```

You can adjust them in the Config class from the ''main.py''.



If you want to run the model, use the command:

```shell
python main.py
```



## Outputs

Update: You can find the outputs of our model in the "outputs" folder.
here is the ckpt for imdb and yelp dataset: [ckpt.rar](https://drive.google.com/file/d/1hSK5w6WKAnQMl1XEutmNAQKyq1_ZrPY1/view?usp=sharing)