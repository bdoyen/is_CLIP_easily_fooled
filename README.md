# is_CLIP_easily_fooled
A small ML experiment with CLIP Zero-Shot-Learning Image Classifier using Post-its and natural images of an Egg and a Cat 

![alt text](https://github.com/bdoyen/is_CLIP_easily_fooled/blob/main/egg_postit_word_cat_pred.png?raw=true)


## 🏁 Starting Point
Following the recent image of CLIP (Contrastive Language–Image Pre-training) model fooled by an image of a green apple with a Post-it where 'IPod' is written down, we have tried to see whether such 'typographical attack' on the model could be replicated with other objects and settings.

Upon our results, it seems that the model's outputs are clearly sensitive to textual data written down a Post-it or directly on the object, but maybe not to the point that has been presented with the apple/Ipod example.


## 🧪 Experiments
We focus our interest on two categories of object : an Egg and a Cat.
These categories have the advantage to be more 'orthogonal' between eachother compared to an apple and an IPod, as the IPod is itself a famous product of a firm called 'Apple'.

5 different experimental settings have been tested:
- [Experiment #1](https://github.com/bdoyen/is_CLIP_easily_fooled/blob/main/experiment_1.JPG): A 'corrupted' egg object placed in the middle of a basic 'desk scenery'.<br/>
With our without Post-its on the egg directly and writtings of the word 'CAT' or drawings of a cat face on the egg also.<br/>
Binary classification and Multi-classes results have been tested.

- [Experiment #2](https://github.com/bdoyen/is_CLIP_easily_fooled/blob/main/experiment_2.JPG): A 'corrupted' egg object placed in the 'desk scenery'
The same egg with or without corruption has been positionned besides a Post-it with the word 'CAT' or a drawing of a face of a cat.<br/>
Secondly, the Post-it alone with writting or drawing for binary and multi-classes classification

- [Experiment #3](https://github.com/bdoyen/is_CLIP_easily_fooled/blob/main/experiment_3.JPG): A 'corrupted' egg object with writtings or drawings on it in a 'plain scenery' (no other object)

- [Experiment #4](https://github.com/bdoyen/is_CLIP_easily_fooled/blob/main/experiment_4.JPG): A 'corrupted' egg object with writtings or drawings on Post-its only in a 'plain scenery' (no other object).<br/>
Specific parts of the egg have been selected in this experiment and not the whole egg: above only, below only or below with right side.

- [Experiment #5](https://github.com/bdoyen/is_CLIP_easily_fooled/blob/main/experiment_5.JPG): A real cat and a 'corrupted' egg object with or without drawings on it in a 'poor scenery' (no clear object)


## 📊 Results 

- From [experiment #1](https://github.com/bdoyen/is_CLIP_easily_fooled/blob/main/experiment_1.JPG) and beginning of [experiment #2](https://github.com/bdoyen/is_CLIP_easily_fooled/blob/main/experiment_2.JPG) (egg besides a Post-it), we can deduce that the model is not very sensitive to the corruption with writting or drawing on the egg or on a Post-it in the case of an object in the middle of the desk scenery.
Using multi-classes classification, we can indeed see that the model predictions are more oriented towards the desk or paper support.

- From the end this experiment (Post-it only), the model's predictions seems more robust towards the writting of the word 'CAT' rather than to the drawing when comparing results on a multi-class classification task

- From [experiment #3](https://github.com/bdoyen/is_CLIP_easily_fooled/blob/main/experiment_3.JPG), we obtain a confirmation of this claim as the model seems more fooled when the word 'CAT' is written down on the egg rather than when a face of a cat is drawed on the egg.

- From [experiment #4](https://github.com/bdoyen/is_CLIP_easily_fooled/blob/main/experiment_4.JPG), the fooling is on the contrary realized with the drawing on a Post-it and with only the lower part of the egg present on the input image.

- Finally, from [experiment #5](https://github.com/bdoyen/is_CLIP_easily_fooled/blob/main/experiment_5.JPG), the model output seems to be strongly influenced by the order of positions of objects on the image (foreground or background)


## 💭 Interpretation

- When a significant part of the egg object can be seen on the image, fooling is better achieved with the written word 'CAT' and not the cat drawing on the egg, which seems to be counter-intuitive and would need further investigations.
- This inverse result is observed with writting and drawing on Post-it : fooling seems then easier with a Post-it rather then the textual data written down on the object directly.
- Fooling was not that easy feasible with these objects and settings compared to the green apple/IPod setting: a close up view of the egg with a Post-it with the word 'CAT' leads to a 94% prediction score for 'egg' category.<br/>
It took some efforts and imagination to fool the model finally...
- Model output scores can flip easily between a class and another if a part of the object (her egg) is revealed or not.


## 💡 Discussion & Conclusion

Larger tests are of course needed to support or not these results, especially the influence of writting/drawing on object or Post-it.<br/>
Also, on the influence of categories inclusion or proximity : is CLIP fooled in the apple/IPod experiment because of the name of the firm 'apple' or not ? <br/>
Can we reproduce such results ?<br/>
Nevertheless, the obtained results show that fooling CLIP model is not as easy as presented with the green apple/IPod experiment for certain objects and settings.<br/>
In the tested cases, the model outputs seems very robust, maybe sometimes too 'robust' ? Especially with the cat in the background of the image with the egg (corrupted and not corrupted egg).<br/>
And even with strong corruption of the egg object, the final prediction remains the same (egg)<br/>
Finally, the same experiment with observation of heatmaps of last layers of the model before classification would make the interpretation of the results easier.


## 📚 References
- starting point : https://www.theverge.com/2021/3/8/22319173/openai-machine-vision-adversarial-typographic-attacka-clip-multimodal-neuron
- CLIP blog post : https://openai.com/blog/clip/
- CLIP in the browser : https://clip.kiri.ai/ 


Photo courtesy of the white persian cat 🐈
