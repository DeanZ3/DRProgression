# DRProgression

Purpose:
	To produce accurate machine learning models using Google Cloud’s AutoML for prediction of diabetic retinopathy (DR) worsening and to use saliency maps and determine anatomical features that contribute to progression.

Methods:
	Models were trained to predict no, mild, and moderate NPDR progression at nodal hours of 16, 24, and 32. The AutoML used an 8-1-1 train-validate-test split of the training data to create a model, fine tuned the hyperparameters, and tested the model. We then validated the model with an external holdout set and analyzed the sensitivity (SN), specificity (SP), positive predictive value (PPV), negative predictive value (NPV), and prevalence. We further explored training modles that predicated progression from a mixed DR training dataset that included different baseline DR grades and training the left and right eyes separately. Lastly, the models that had the best results were replicated 4 more times.

Results:
	With a set threshold of 0.70 for SN and SP, we produced models for mild and moderate NPDR that met the requirements at 24 node hours. The SN, SP, PPV, NPV, and prevalence of our best mild NPDR model was 0.70, 0.72, 0.31, 0.93, and 0.15, respectively. Additionally, the SN, SP, PPV, NPV, and prevalence of our average moderate NPDR model was 0.82, 0.74, 0.38, 0.93, and 0.22, respectively. The datasets that used multiple DR grades to produce progression models failed to reach our 0.70 threshold for SN and SP. Lastly, there was no statistically significant difference in training models with left eye and right eye images.

Conclusion:
	This study demonstrates the accuracy and potential of autoML in DR eye progressions. The models creations works best with individual DR grades. In the real world, an accurate autoML model may lead to more effective diagnosis and treatment for patients with not yet progressed DR and a more cost effective solution in the healthcare system.

Saliency Map Template:
  Copy this to Drive
  https://colab.research.google.com/drive/1_Z9eFTWAV5R79bSog6m0GXcK061OyDo9#offlin
