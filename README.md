# Detecting Burglars And Wild Animals In CCTV Footage Using Deep Learning Models On Microcontroller Boards

## Introduction
There are two main culprits responsible for home invasions - burglars and wild animals. Provided that there is no one present at home to interfere, both of them can easily bypass the conventional prevention methods such as locked doors and fences. Conventional CCTV cameras are not helpful because they only record the crime footage that can be used later by police but does not stop the crime from happening. A better solution would be to have a device that can continuously monitor the CCTV feed and search for either of those two possible threats and take actions such as contacting homeowners, police, set off alarms, etc. Since CCTV cameras are already installed in most of the places, the focus is on designing a downstream device that can directly take the stream from CCTV as an input.

## Scope
Design an electromechanical device that can:
* The CCTV cameras are usually connected to the TV/monitors through a hdmi cable. The device should connect between the hdmi cable and TV. As such, it should be small enough as the size of the TV adapter or set-top box.
  * This would require the device to have a credit-card size computer such as Beaglebone or Raspberry-Pi. Both of them have on-board Linux. Check [1](https://community.arm.com/arm-community-blogs/b/architectures-and-processors-blog/posts/high-accuracy-keyword-spotting-on-cortex-m-processors?utm_source=Social-organic&utm_medium=Twitter&utm_campaign=keywordaccuracy) and [2](https://github.com/ARM-software/ML-KWS-for-MCU/tree/master/Deployment) below for information on how to run DL models on Cortex-M processor on Beaglebone.
* The device should accept streaming video feed as an input.
* Sample images from the video every given timestep.
* Run object detection on the sampled images using open-source state-of-the-art models.
  * The classification network should be 'lightweight' enough to run on Beaglebone or Raspberry Pi. One such model is mentioned in [Efficient Convolutional Neural Networks on Raspberry Pi for Image Classification](https://paperswithcode.com/paper/triplenet-a-low-computing-power-platform-of) (repo cloned at C:\Users\Pankaj\TripleNet).
  * Networks with weights can be directly used as per https://pytorch.org/vision/stable/models.html
* Perform a set of action if the targeted object is detected.

## References:
1. [How to Achieve High-Accuracy Keyword Spotting on Cortex-M Processors](https://community.arm.com/arm-community-blogs/b/architectures-and-processors-blog/posts/high-accuracy-keyword-spotting-on-cortex-m-processors?utm_source=Social-organic&utm_medium=Twitter&utm_campaign=keywordaccuracy)
2. [Core for Keyword Spotting on Arm Cortex-M boards](https://github.com/ARM-software/ML-KWS-for-MCU/tree/master/Deployment)
3. [Effectiveness of non-lethal predator deterrents to reduce livestock losses to leopard attacks within a multiple-use landscape of the Himalayan region](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7384438/)
4. [Ultrasonic deterrents reduce nuisance cat (Felis catus) activity on suburban properties](https://doi.org/10.1016/j.gecco.2018.e00444)
5. [A global view on evidence-based effectiveness of interventions used to protect livestock from wild cats](https://doi.org/10.1111/csp2.317)

