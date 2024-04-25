![trad(1)](https://github.com/eyatab/Fundus-images-segmentation-using-Attention-VggUnet3-/assets/79045818/28748d09-2f1c-43d4-bb64-1f58e993d18f)# Fundus-images-segmentation-using-Attention-VggUnet3+  
Application du modèle Attention Unet 3+ intégrant l’apprentissage par transfert   

![tl](https://github.com/eyatab/Fundus-images-segmentation-using-Attention-VggUnet3-/assets/79045818/ea893cb8-7ddb-4b81-84b5-848af1c7c3be)   
L’opération de l’apprentissage par transfert utilisant l’extraction de caractéristiques est effectuée
en trois étapes :
1. La première étape consiste à choisir et charger le modèle pré-entrainé que nous souhaitons
utiliser comme base de notre entrainement en fonction de la tache à accomplir .  
Avec la bibliothèque Keras de Tensorflow, il est simple de récupérer le modèle déjà entrainé par défaut sur ImageNet.
3. Geler les couches initiales du modèle pré-entrainé pour ne pas perdre l’apprentissage qui a
déjà eu lieu.
4. Entrainer le modèle sur l’ensemble de données Refuge.   
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------   
*Apprentissage par transfert ( Transfer learning): 
![trad(1)](https://github.com/eyatab/Fundus-images-segmentation-using-Attention-VggUnet3-/assets/79045818/d51b27ab-7337-479f-9ef8-e70fc9403dab)    

- Extraction de caractéristique (Feature Extraction) : Dans cette approche, on retire la dernière couche entièrement connectée du modèle pré-entrainé, figeant ainsi tous les
autres couches du réseau. Ensuite, les informations extraites par les couches pré-entrainées sont utilisées comme entrée pour un nouveau classifieur spécifique à la tache cible.
Etant donné que les couches pré-entrainées ont déjà appris des caractéristiques utiles pour la tache source, cette approche permet au modèle de se concentrer sur l’adaptation aux
spécificités de la tache cible. L’un de ses avantages est sa rapidité, et elle nécessite moins de données d’entrainement que la méthode de FT.   
![fe(1)](https://github.com/eyatab/Fundus-images-segmentation-using-Attention-VggUnet3-/assets/79045818/4d6542fd-530c-4380-9905-2379ac3377cf)  
Source TL:   
https://www.tensorflow.org/tutorials/images/transfer_learning

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------  
Résultats :   
![res (2)](https://github.com/eyatab/Fundus-images-segmentation-using-Attention-VggUnet3-/assets/79045818/e16f76fd-8f2e-4fae-8a29-2976dad44a2c)


