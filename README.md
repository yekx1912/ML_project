# Change Attribute of Face Image with GAN
## Important
We have introduce and analysis our project more detail in ML_project.ppt

## Data set
We choose the first 40000 Align&Cropped Face Images in [CelebA](http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html) for training with their gender attribute  

## ICGAN
[ICGAN](https://arxiv.org/abs/1611.06355) introduce an encoder to determine specific representation of generated images, which 
inverse the mapping of cGAN, given an input image x, to obtain its representation as a latent variable z and a conditional vector 
y, and we can modify z and y to re-generate the original image with complex variations.

### Loss function
* train cgan:  
  * D_loss = -(log(D(x,y)) + log(1-D(G(z,y'),y')))
  * G_loss = -log(D(G(z,y),y))
* train enz:
  * z_loss = l2_loss(z-enz(G(z,y')))
* train eny:
  * y_loss = l2_loss(y-eny(x))

### architecture
<img src=https://github.com/poetic1912/ML_project/blob/master/icgan_architecture.png>  

image source:[ICGAN Paper](https://arxiv.org/abs/1611.06355)

### result
<div align=center>
<img src=https://github.com/poetic1912/ML_project/blob/master/result.jpg>
</div>


