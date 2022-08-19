Performance Engineering &mdash; Image Processing Optimisation
==============================================================

Processing images fast and hardware-efficient is the core of our success.
Thus we want your help in improving our algorithms.
If you are solving this challenge as part of our *interview process*, please read [the detailed instruction](Hiring.md).  

**The goal of this challenge is to implement the fastest parallelised algorithm to blur the people (segmentation) in the images provided.**

<table>
<thead>
  <tr>
    <th>Original</th>
    <th>Blurred</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td><img src="assets/sample/original.jpeg" alt="original image"></td>
    <td><img src="assets/sample/blurred.jpeg" alt="blurred image"></td>
  </tr>
</tbody>
</table>

<small>Image credit: Photo by [Omar Lopez](https://unsplash.com/photos/rwF_pJRWhAI) on [Unsplash](https://unsplash.com/).</small>

The winner of [the bimonthly leaderboard](./Leaderboard.md) will be awarded a prize 🏆 in the form of an Amazon voucher.

Don't hesitate to [write us](mailto:hello@celantur.com) if you have any questions concerning the challenge.

The Task
--------

Implement the blurring algorithm in C/C++ (CUDA). Use a median blur with kernel size 161.

Dockerise your application using `nvidia/cuda:11.3.1-runtime-ubuntu20.04` as base image. The application itself should not be larger than 20 MiB. 

Make the blurring process as fast as possible (given the hardware constraints). 
Use multiprocessing or multithreading, memory optimisation or any other technique that you see fit. 

You can download the images and segmentation masks using [`download_coco_images.ipynb`](./download_coco_images.ipynb).
Images are selected from the [COCO Dataset](https://cocodataset.org/#explore).

<!--The COCO API provides [C code](https://github.com/cocodataset/cocoapi/blob/master/common/maskApi.c) to turn the segmentation annotation into binary mask (numpy 2D array), cf [coco.py](https://github.com/cocodataset/cocoapi/blob/8c9bcc3cf640524c4c20a9c40e89cb6a2f2fa0e9/PythonAPI/pycocotools/coco.py#L434).-->

Provide us with information how to set up and run your code.

Share your code with the [Celantur Bot](https://github.com/celantor).


Prize
------------

Every 2 months, our engineering team will select the winner, who will receive a **€150 Amazon Voucher Card** (10 minimum participants). Share the challenge with your friends and acquaintances using this link:   

Note that the leaderboard will be reset every 2 months. It is not possible to receive multiple voucher cards with the same code submission.


Evaluation
------------

The reference hardware on which the algorithm will be tested is a [p3.2xlarge](https://aws.amazon.com/ec2/instance-types/#Accelerated_Computing) with
- 1 NVIDIA Tesla V100 (16 GiB)
- 8 vCPUs: Intel Xeon Scalable Processor (Broadwell E5-2686 v4)
- 61 GiB Memory

The OS is **Linux** / Ubuntu 20.04 LTS (Focal Fossa). 

Your code will be reviewed by at least three of our engineers. The aspects of your code we will judge include:
- **Performance**: Does the code do what was asked? If there is anything missing, does the README explain why it is missing?
- **Code Quality**: Is the code simple, easy to understand, and maintainable?
- **Technical Choices**: Do choices of libraries, algorithms, and architecture seem appropriate for the challenge?
