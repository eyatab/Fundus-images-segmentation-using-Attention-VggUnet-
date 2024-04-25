Les défis de la segmentation du disque optique (OD) et de la cupule optique (OC):   

- Les images médicales sont obtenues à partir de différentes modalités d’imagerie médicale et sont fréquemment affectées par divers problèmes liés au traitement d’image, tels que le bruit et les problèmes de contraste, qui posent encore des défis ouverts (Martins, Cardoso, & Soares,2020). Ces problèmes de qualité d’image compliquent davantage la segmentation du disque optique et de la cupule optique, qui est déjà un défi complexe dans le domaine de l’analyse d’images ophtalmologiques.  
- Le disque optique présente des variations significatives en termes de forme, de taille et meme de couleur (Haider et al., 2023).   
- Les contours de la cupule optique peuvent etre flous, avec des contrastes inégaux et discontinus en raison de la présence de vaisseaux sanguins.   
- La qualité de l’image de fond d’œil joue un role crucial dans la précision de la segmentation. Les images du fond d’œil rétinien provenant de différentes caméras présentent des variations importantes en termes de valeurs d’intensité de pixel, et d’effets d’arrière-plan qui rendent la segmentation difficile (Sivaswamy et al., 2015).   
--> Par la suite, pour faire face à ces défis, il est crucial de donner une attention particulière au pré-traitement des images rétiniennes afin d’améliorer la
qualité des images et faciliter le processus de segmentation.     
Références : 
* Haider, A., Arsalan, M., Park, C., Sultan, H., & Park, K. R. (2023). Exploring deep feature blending capabilities to assist glaucoma screening. Applied Soft Computing, 133 , 109918.     
* Martins, J., Cardoso, J. S., & Soares, F. (2020). Offline computer-aided diagnosis for glaucoma detection using fundus images targeted at mobile devices. Computer Methods and Programs in Biomedicine, 192 , 105341.   
*Sivaswamy, J., Krishnadas, S., Chakravarty, A., Joshi, G., Tabish, A. S., et al. (2015). A comprehensive retinal image dataset for the assessment of glaucoma from the optic nerve head analysis. JSM Biomedical Imaging Data Papers, 2 (1), 1004.     
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------    
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


