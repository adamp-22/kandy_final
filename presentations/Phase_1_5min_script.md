# Phase I presentation script

Five-minute talk. Slides 1–13 are the main presentation. Slides 14–17 are backup figures for questions.

The timings are a guide for practice. The main script has 637 words.

## Slide 1 · What fools an AI-image detector?

**0:00–0:20**

Our task is to tell real photos and AI-generated images apart. We wanted to see if small changes to an image could fool the models. We also wanted to know if both models make the same mistakes, and what might explain those mistakes.

## Slide 2 · How we shared the work

**0:20–0:40**

We did not work as two separate pairs. After two members left, my teammate and I shared the tasks. We both made some of the standard plots and some of the AI-assisted plots. We used the same images and models for both parts.

## Slide 3 · A first look at the data

**0:40–1:05**

We used a dataset called CIFAKE. After removing duplicate images from training, we had about eighty-nine thousand training images, ten thousand validation images and twenty thousand test images. We first looked at examples and how sharp the images were. The AI-generated images were often sharper, but this did not clearly separate the two groups.

## Slide 4 · Training and choosing the models

**1:05–1:35**

We trained a small CNN from scratch. For ResNet18, we started with a model already trained on ImageNet and trained it further on our data. We chose CNN round nineteen and ResNet round five because they had the lowest validation loss. Validation accuracy was about ninety-five and ninety-eight percent. We then stopped training and tested image changes.

## Slide 5 · How we changed the images

**1:35–2:00**

We compressed, blurred, resized and sharpened the images. We also added noise and made the colours stronger or weaker. Then we tried blur followed by sharpening or weaker colours. We kept the models and the fake-or-real cutoff the same, so we could see what each image change did.

## Slide 6 · Part A: same image, different answers

**2:00–2:15**

Here are two examples, one for each model. Both images are fake. After blur or resizing, the models call them real. We chose these examples because the change was large. The next plots show how often this happens.

## Slide 7 · Part A: blur and resizing hide many fakes

**2:15–2:40**

With blur at zero-point-six, the CNN found only thirty-four percent of the fakes, and ResNet found twenty-seven percent. Making images smaller and then larger fooled the models even more. ResNet was better on the original images, but these edits caused a bigger drop in its results.

## Slide 8 · Part A: each image reacts differently

**2:40–3:00**

Each thin line follows one fake image as we add more blur. The orange line shows the average for all five thousand. Some scores fall quickly. Others stay high or go up again. Looking only at the average would hide this.

## Slide 9 · Part A: do both edits fool the model?

**3:00–3:20**

Each dot shows one image after blur and after resizing. Dots in the bottom-left corner fool the model with both edits. This happens for about sixty-five percent of fakes with the CNN and seventy-two percent with ResNet. So the two edits often fool the model on the same images.

## Slide 10 · Part B: does sharpness matter?

**3:20–3:45**

In the AI-assisted part, we looked more closely at sharpness. Sharpening the blurred fakes helped both models find about ninety-eight percent again. But sharpening real photos also made the models call many of them fake. Added noise gave different results, so sharpness alone does not explain all the mistakes.

## Slide 11 · Part B: colour and different objects

**3:45–4:05**

We then made the colours weaker after blurring the images. We compared groups such as dogs, cars and birds. The models missed more fakes in some groups, especially the CNN. Changing colour without blur had less effect. So colour seems to matter more after blur.

## Slide 12 · Part B: a map of image features

**4:05–4:35**

PCA turns four image features into a simple map: brightness, contrast, colour strength and sharpness. Similar images tend to be close together. Each chart shows the same thousand images. The dots stay in place, but their colours change when we blur the images. This map keeps about seventy-four percent of the differences in these features. High and low scores still mix, so the map does not fully explain the mistakes.

## Slide 13 · What we found

**4:35–5:00**

The standard plots showed when the models make mistakes and which images fool them with both edits. The AI-assisted plots helped us look for reasons. Our main finding is that a model can do well on the original images and still struggle after small edits. Sharpness matters, but it is not the whole explanation.

## Backup slides

### Slide 14 · CNN: one image, four predictions

We picked these examples because the scores changed a lot. The fake image gets a much lower fake score after blur. The real photo gets a much higher fake score after sharpening. A score above fifty percent means the model calls the image fake. Each row shows the same image.

### Slide 15 · ResNet18: one image, four predictions

We picked these examples because the scores changed a lot. The fake image gets a much lower fake score after blur. The real photo gets a much higher fake score after sharpening. A score above fifty percent means the model calls the image fake. Each row shows the same image.

### Slide 16 · More tests: JPEG compression and noise

We also tested JPEG compression and added noise. The two charts use different scales, so we compare the models within each chart. Strong noise gives a different result from blur or resizing. This is another reason why sharpness alone does not explain the predictions.

### Slide 17 · Sharpness after five kinds of edits

These charts compare five kinds of edits using the same sharpness measure. Each point sums up five thousand real or fake images. Noise does not always follow the same pattern as the other edits. These group averages cannot tell us exactly what the model uses inside the network.
