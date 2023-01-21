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
  
  
  4- Création d'un nouveau signal xnoise, en introduisant un bruit blanc gaussien dans le signal d’origine x(t)
  
