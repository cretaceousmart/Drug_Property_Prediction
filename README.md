# Drug_Property_Prediction

Hi, I’m happy to let you know I’ve finished the coding task that builds the Transformer, GNN, and Tree model(Random Forest) to predict the drug property. Thanks for giving me this opportunity to slove real-world problems since I haven’t gotten in torch with Medical ML problems and  Transformer. I will show you what I’ve done and what I found.

- Due to the limited time, there're a lot of things that can be improved, I'm looking forward to having a furthur discussion with you!

- Outcome: All the experiment's outcomes are shown in the .ipynb. Since I don't have a nice GPU, I put all the training processes on Colab. I will suggest you check them by the below link:

  - [Transformer](https://colab.research.google.com/drive/1Jx4fV3IADJjntRejNWnKtMTwYAe4k7b8?usp=sharing)
  - [GNN](https://colab.research.google.com/drive/1-NuprDN1gfcmqjRCwYVRVhtRte5MJu4b?usp=sharing)
  - [Tree model](https://colab.research.google.com/drive/1mhTdbYw4DtNfkekEuJtF3ElSX5XT9l2h?usp=sharing)
  

- Timeline:
    - 2022.12.6-12.9: Read the description of the task. In the beginning, I found an implementation for this problem called [Deep Purpose](https://github.com/kexinhuang12345/DeepPurpose/blob/master/README.md#pretrained-models). However, since I don’t know anything about drug featurization and transformer/attention, so I spend about 1.5 days learning it.  And decide to spend about 2 days writing it from scratch by Pytorch. Including the network (multihead-attention, encoder, decoder), data loader, data spliting, data shuffle, and plotting …)
    - 2022.12.13: After an email with Ryan, I realized that I can use the implementation from other people, so I use the implementation from Deep Purpose to build GNN. For the tree model, I use a library called [DeepChem](https://github.com/deepchem/deepchem) to do the drug structure featurization. (Choose one of the featurizer) and use scikit-learn to build XGBoost and Random Forest.
    - 2022.12.14: summarized the result
    - Basically I spend most of my time writing Transformer.


- What interesting things I found:
  - Data Shuffle is neccessary in this task
  - Featurization (Drug structure embedding) is important (but I didn't choose the featurizer carefully due time limited)
  - Batch size need to be small (like 32) and epoch number need to be large (like 300)
  - Transformer is trained fastest due Parallel Computing
  - Model comparasion：It's hard to compare since I don't spend much time in tunning the parameters


- About model:
    - For Transformer: I build it from scratch without using any other library. In the beginning, I don’t know how to embed the drug structure in a proper way. So for the Transformer, I just use a very naive NLP method for featurization (maybe missed the information about the drug structure ).  I don't spend much time tuning the parameters but it achieves the comparable performance as the implementation in Deep Purpose.
      - ![image](https://user-images.githubusercontent.com/48281792/207720048-1ec6b967-cc71-4ca7-9b02-d5c9acab3c8b.png)
      - ![image](https://user-images.githubusercontent.com/48281792/207720152-4b7349ab-31fd-4e58-8df2-40b630cf9ccc.png)

      
    - For GNN, I use the implementation from Deep Purpose and plot the ROC curve.
    - For Tree model, I use the featurizer from DeepChem and use scikit-learn to build model,then plot the ROC curve.
  

  
