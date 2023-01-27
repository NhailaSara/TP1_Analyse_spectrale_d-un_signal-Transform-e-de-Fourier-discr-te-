# TP1- Analyse spectrale d’un signal_Transformée de Fourier discrète
Représentation des signaux et applications de la transformée de Fourier discrète (TFD) sous Matlab.

<B>Réalisé par:</B>
*Sara NHAILA

<B>Encadré par : </B>
*Mr Alae Ammour

<B>Introduction</B>

<B>Objectifs</B>
-Représentation de signaux et applications de la transformée de Fourier discrète (TFD) sous Matlab.
-Evaluation de l’intérêt du passage du domaine temporel au domaine fréquentiel dans l’analyse et l’interprétation des signaux physiques réels.

<H1>Partie 1 :Représentation temporelle et fréquentielle</h1>
* pour calculer la transformé de fourier a temps discrète sur des signaux suivant le temps on va appliquer la transformée de fourier discrète 

Considérons un signal périodique x(t) constitué d’une somme de trois sinusoïdes de fréquences 440Hz, 550Hz, 2500Hz.


on a 𝐱(𝐭)=𝟏.𝟐𝐜𝐨𝐬(𝟐𝐩𝐢𝟒𝟒𝟎𝐭+𝟏.𝟐)+𝟑𝐜𝐨𝐬(𝟐𝐩𝐢𝟓𝟓𝟎𝐭)+𝟎.𝟔𝐜𝐨𝐬(𝟐𝐩𝐢𝟐𝟓𝟎𝟎𝐭)

1- Tracer le signal x(t). Fréquence d’échantillonnage : fe = 10000Hz, Intervalle : Nombre d’échantillons : N = 5000.
![alt text](https://github.com/NhailaSara/TP1_Analyse_spectrale_d-un_signal-Transform-e-de-Fourier-discr-te-/blob/main/TD1_1.1.png?raw=true)
![alt text](https://github.com/NhailaSara/TP1_Analyse_spectrale_d-un_signal-Transform-e-de-Fourier-discr-te-/blob/main/TD1_1.2.png?raw=true)
<BR>
2- Calculer la TFD du signal x(t) en utilisant la commande fft, puis tracer son spectre
![alt text](https://github.com/NhailaSara/TP1_Analyse_spectrale_d-un_signal-Transform-e-de-Fourier-discr-te-/blob/main/TD1_2.2.png?raw=true)
![alt text](https://github.com/NhailaSara/TP1_Analyse_spectrale_d-un_signal-Transform-e-de-Fourier-discr-te-/blob/main/TD1_2.png?raw=true)

on va obtenir 6 piques , car la transformée de fourier représente la symétrique conjugué, le spectre est toujours symétrique par rapport a la frequnace d'echantillonage
  
3. Pour mieux visualiser le contenu fréquentiel du signal, utiliser la fonction fftshift, qui effectue un décalage circulaire centré sur zéro du spectre en amplitude obtenu par la commande fft.
  
  ![alt text](https://github.com/NhailaSara/TP1_Analyse_spectrale_d-un_signal-Transform-e-de-Fourier-discr-te-/blob/main/TD1_.3.2.png?raw=true)
  ![alt text](https://github.com/NhailaSara/TP1_Analyse_spectrale_d-un_signal-Transform-e-de-Fourier-discr-te-/blob/main/TD1_.3.png?raw=true)
  
  
  4- Création d'un nouveau signal xnoise, en introduisant un bruit blanc gaussien dans le signal d’origine x(t).
  Utilisation de la commande <b>randn</b> pour générer ce bruit.
  Il est à noter qu’un bruit blanc est une réalisation d'un processus aléatoire dans lequel la densité spectrale de puissance est la même pour toutes les fréquences de la bande passante. Ce bruit suit une loi normale de moyenne 0 et d’écart type 1.
  ![alt text](https://github.com/NhailaSara/TP1_Analyse_spectrale_d-un_signal-Transform-e-de-Fourier-discr-te-/blob/main/tp1_4.png?raw=true)
  ![alt text](https://github.com/NhailaSara/TP1_Analyse_spectrale_d-un_signal-Transform-e-de-Fourier-discr-te-/blob/main/tp1_4.png?raw=true)
  
  
  5 – Utiliser la commande sound pour écouter le signal et puis le signal bruité.

  pour écouter le bruit on utilise : <b>sound(xnoise)</b>, <b>sound(x+xnoise)</b>.
La puissance du signal en fonction de la fréquence (densité spectrale de puissance)est une métrique couramment utilisée en traitement du signal. Elle est définie comme étant le carré du module de la TFD, divisée par le nombre d'échantillons de fréquence.
  
6- Calculez puis tracer le spectre de puissance du signal bruité centré à la fréquence
![alt text](https://github.com/NhailaSara/TP1_Analyse_spectrale_d-un_signal-Transform-e-de-Fourier-discr-te-/blob/main/6_AFF.png?raw=true)
![alt text](https://github.com/NhailaSara/TP1_Analyse_spectrale_d-un_signal-Transform-e-de-Fourier-discr-te-/blob/main/6_CODE.png?raw=true)

  Interprétation de résultat obtenu après augmentation de l’intensité de bruit :
  ![alt text](https://github.com/NhailaSara/TP1_Analyse_spectrale_d-un_signal-Transform-e-de-Fourier-discr-te-/blob/main/interpretation_6.png?raw=true)
  
  <H1>Partie 2: Analyse fréquentielle du chant du rorqual bleu</H1>
  
  

    Introduction :

        Il existe plusieurs signaux dont l’information est encodée dans des sinusoïdes. Les ondes sonores est un bon exemple. Considérons maintenant des données audios collectées à partir de microphones sous - marins au large de la Californie. On cherche à détecter à travers une analyse de Fourier le contenu fréquentiel d’une onde sonore émise pas un rorqual bleu.

        Les rorquals bleus accordent leurs vocalises de basse fréquence de manière extrêmement précise et uniforme, à une fréquence de 16 Hz, selon l’étude récemment publiée dans le Journal of the Acoustical Society of America

        Le but de cet exercice est d’extraire le chant du rorqual bleu du fichier ‘bluewhale.au’ .Ce chant se trouve entre les deux fréquences x=2.45e4 z=3.1e4 après on l entend a travers la commande sound et finalement on le trace avec la commande plot dans un intervalle de temps t=15*(0:1/Fs:(length(rorqualvoice)-1)*(1/Fs))

  <B>1-Chargez, depuis le fichier ‘bluewhale.au’, le sous-ensemble de données qui correspond au chant du rorqual bleu du Pacifique.</B>
  
  On utilise la commande audioread pour lire le fichier. Le son à récupérer correspond aux indices allant de 2.45e4 à 3.10e4 Voila un aperçu sur le code :
  ![alt text](https://github.com/NhailaSara/TP1_Analyse_spectrale_d-un_signal-Transform-e-de-Fourier-discr-te-/blob/main/P2_1.png?raw=true)
  
  2- Ecoutez ce signal en utilisant la commande sound, puis visualisez-le.
  
    * En effet, les appels de rorqual ble sont des sons à basse fréquence, ils sont à peine audibles pour les humains. Pour ces raison on multiplie l'axe temporel en 10
    * On rappelle que la bande de fréquences audibles par l’oreille humaine s’étale de 20 Hz à 20kHz. Lorsque la fréquence est faible, le son est grave (de 20 à 200 Hz). On parle de son médium pour une fréquence comprise entre 200 et 1000 Hz et de son aigu lorsque la fréquence est comprise entre 1000 et 15000 Hz Voila un aperçu sur le code :
  
  ![alt text](https://github.com/NhailaSara/TP1_Analyse_spectrale_d-un_signal-Transform-e-de-Fourier-discr-te-/blob/main/P2_2.png?raw=true)
   ![alt text](https://github.com/NhailaSara/TP1_Analyse_spectrale_d-un_signal-Transform-e-de-Fourier-discr-te-/blob/main/p2_2_aff.png?raw=true)
 
  
  3- Spécifiez une nouvelle longueur de signal n qui sera une puissance de 2, puis tracer la densité spectrale de puissance du signal.
  Pour identifier les composantes fréquentielles de ce signal audio ,on applique la transformée de Fourrier
  ![alt text](https://github.com/NhailaSara/TP1_Analyse_spectrale_d-un_signal-Transform-e-de-Fourier-discr-te-/blob/main/p3_3_sc.png?raw=true)
  Comme vous remarquer dans les lignes de code le signal subit une compression / 10 pour visualiser les fréquences réelles du gémissement de rorqual bleu.
  ![alt text](https://github.com/NhailaSara/TP1_Analyse_spectrale_d-un_signal-Transform-e-de-Fourier-discr-te-/blob/main/p3_3_aff.png?raw=true)
  
  4- Déterminer à partir du tracé, la fréquence fondamentale du gémissement de rorqual bleu.
  
  On observe une fréquence fondamentale qui est conforme a celle des rorquals bleus qui accordent leurs vocalises de basse fréquence de manière extrêmement précise et uniforme, à une fréquence de 16 H
  
  ![alt text](https://github.com/NhailaSara/TP1_Analyse_spectrale_d-un_signal-Transform-e-de-Fourier-discr-te-/blob/main/4_fin.png?raw=true)
Conclusion:
  Dans ce Tp ,nous avons pu découvrir la représentation de signaux et les applications de la transformée de Fourier discrète (TFD) sous Matlab. Ainsi que , l’évaluation de l’intérêt du passage du domaine temporel au domaine fréquentiel dans l’analyse et l’interprétation des signaux physiques réels.
