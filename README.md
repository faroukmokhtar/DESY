# Graduation Project

This work was produced at the DESY site under the supervison of Dr. Dirk Kruecker and Dr. Isabell Melzer-Pellmann, for a duration of two months. 

# <ins>Abstract<ins>
In the inclusive single-lepton search published by CMS [1] for 36.5 f b − 1 of 13 TeV proton-proton collisions data, a Data-Driven Background Estimation was performed. This search may be improved by the use of machine learning techniques, and to be able to perform similar Data-Driven Background Estimation, the classifier output have to be uncorrelated to one of the event parameters with good signal-to-background separation. To achieve such classification an Advesarial Network was constructed, studied and tested on the same simulation data which was used in the SUSY search by CMS [1].
 
![example](/images/CMS.png)
  
# <ins>Introduction<ins>
Adversarial Networks were first introduced in 2014 [2], and later developped and used
for the first time in physics in LHC analysis [3]. An Adversarial Network consists of
two Neural Networks: a classifier and an adversary. The classifier is given input data X,
with the task of separating signal from background events, while the adversary tries to
ensure that the classifier output is independent of one of the features: Z ∈ X or Z(X).
This comes at the expense of classification efficiency. Due to the brought about loss in
efficiency, the adversary is said to have confused the classifier.

The two networks are coupled in a way that the training is done simultaneously, and
the combined loss to be minimized is given by:

_**loss = loss<sub>clf</sub> − λ · loss <sub>adv</sub>**_

The parameter λ is accordingly added to the network hyper-parameter space to be
optimized. It defines the activity of the adversary. A greater value of λ indicates high
adversary activity, which results in high confusion. An optimal value of λ allows for the
decorrelation at the expense of little classification efficiency loss.

__In this problem:__
- X -- The input of the network represents the event parameters (or so called features)
- Y -- The target/label associated with each event. Y=1 represents a signal & Y=0 indicates a background
- Z -- The nuissance paramater, chosen to be dPhi, representing the angle between the reconstructed W-boson and lepton
- Finalweight -- The cross-section of each event

__Goal:__
Use the adversarial network to decorrelate the output of the classifier from the nuissance paramater dPhi.
This decorrelation will be further tested by computing a Ratio that should equal 1 for complete decorrelation.

# <ins>References<ins>
[1] CMS collaboration (2017). Search for supersymmetry in events with one lepton
and multiple jets in proton-proton collisions at sqrt(s) = 13 TeV. Available at:
https://arxiv.org/abs/1609.09386

[2] Goodfellow, I., Pouget-Abadie, J., Mirza, M., Xu, B., Warde-Farley, D., Ozair, S.,
Courville, A., and Bengio, Y. (2014). Generative adversarial nets. https://arxiv.
org/abs/1406.2661

[3] Louppe, G., Kagan, M., and Cranmer, K. (2016). Learning to Pivot with Adversarial
Networks. https://arxiv.org/abs/1611.01046
