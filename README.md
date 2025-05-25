<h1>Formulating Visual Representations of SEM images of
 ZnO-nanorods to Predict Synthesis Conditions using
 Magnification Prior Contrastive Learning</h1>

  <h2>Overview</h2>
  This repository contains the project I worked on as a Research Intern under Mathematical Informatics (MI) Laboratory at Nara Institute of Science and Technology (NAIST) in Ikoma, Japan last
  January 2025. All credits reserved from NAIST with regards to the SEM image dataset I worked on.

<ul>
<h1> Description </h1>
<h2>Introduction</h2>
Zinc Oxide (ZnO) is a semiconductor which has a high thermal and chemical stability,
often used in the form of nanowires/nanorods. This material poses great importance in developing
high-efficiency flexible thermoelectric device. However, determining synthesis conditions of ZnO-nanorods
using laboratory tests are expensive. Thus, this project aims to extract such conditions in ZnO-nanorods
by analyzing SEM images of the said material.

<h2>Method</h2>
By leveraging on a novel Computer Vision model called <span style="color:blue"><strong>Simple Framework for
Contrastive Learning of Visual Representations (SimCLR)</strong></span>, we extract visual representations
from SEM images of ZnO-nanorods and predict its best synthesis conditions.

![Illustration of Positive and Negative Pairs under the SimCLR Architecture](assets/simclr-visualization.png)

SimCLR tries to learn such visual representations by establishing <strong>positive and negative views</strong> of the same image using
data augmentation under Computer Vision. The model then tries to maximize disagreement between negative pairs while simultaneously maximizing agreements between
positive pairs. Then, such values are being translated as a loss function which the model then tries to minimize across the batch of 
SEM images. 

Additionally, I developed a separate model that leverages on <strong>magnification priors</strong> present in the dataset by establishing pairs of images with their
other magnification. This, then, would enable us to not only formulate visual representations but also to establish connections between sets of data with 
varying magnifications.

<h2>Results</h2>
A good learning representation also enabled us to somehow predict the  correct synthesis conditions present in the images. An accuracy of at least
 60% in some runs of the model is a testament of how we can utilize this architecture in analyzing best synthesis conditions of the said material just
 be looking at its SEM images. Additionally, using magnification as a prior condition in establishing positive pairs pose crucial benefits in better predicting synthesis conditions
 of SEM images, as evidenced by a higher and more consistent accuracy.
</ul>

  <h2>Files</h2>
  This repository contains the following files:
  <li><code>MA-final-resnetmodel.ipynb</code>: Base SimCLR model using a specific magnification, with images converted in grayscale</li>
  <li><code>MB-final-resnetmodel.ipynb</code>: Base SimCLR model using a specific magnification, with images in grayscale and greater emphasis (weights) on pairs</li>
  <li><code>MC-final-resnetmodel.ipynb</code>: Magnification-Prior SimCLR model using all magnifications with modified Contrastic Loss</li>
  <li><code>MD-final-resnetmodel.ipynb</code>: Magnification-Prior SimCLR model using all magnifications</li>
 
 
