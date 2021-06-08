## Team: Tweety
### Members: 
Conrad Ciszek
Amir Mola
Jose Becerra
Tejas Bharadwaj

## About the project/competition: 
For our project we decided to use the Kaggle competition about classifying various bird categories. Given 555 different categories of birds, the challenge is to train a supervised machine learning model that is able to detect the category/class of a given image of a bird. The dataset contains about ~38000 images distributed unevenly between the 555 classes. Furthermore, there is not a unique image size for the training data and each image comes in a different dimension. These images are taken from birds in various geographical locations (land, tree, air) with the bird either flying or sitting still.

Our first approach to this problem was to use Transfer Learning to have a better shot at tackling this problem than starting from scratch. After reading a bit more on Pytorch pretrained models and looking at some examples and considering the resources (GPU) and time we have, we decided to work on training resnet50 as our base model. After 15 epochs and before the model starts overfitting, we got around 50% accuracy on the test data on the Kaggle competition which is not super good. Therefore, we decided to focus a bit more on balancing the training data first before starting to fine-tune anymore models.

## Upsampling:
To help boost accuracy of our model and account for overfitting we incorporated a technique called upsampling. Here we went through all the files of the 555 different birds and found the maximum number of images in each folder (106). By taking advantage of the Transforms library in Pytorch, we generated transformed images based on the existing images to increase the number of bird images in each class to the maximum number we got in the previous step. This approach was mainly done to ensure that we have the same number of images in each category and our data is balanced. Some transformations we utilized were random choices of: a horizontal flip, random rotation, and a random grayscale of an image. We did this in hopes of generating more useful data for the model to boost accuracy. Some examples of these transformations can be seen below: 

## More PreTrained Models:
After balancing the data, we decided to return to fine-tuning pre-trained models to improve our accuracy. After reading more about Pytorch pretrained models, we decided to try resnet151, Densenet169, resNext and vgg_bn19. We trained each of these models separately with the new balanced training data and our accuracy results are as follows:

| Model     | Accuracy |
| resnet 151        |    :----: | 
| densenet 151      | Title       | 
| vgg_bn19   | Text |
| resNext | sss |

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/tejaskb04/tejaskb04.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
