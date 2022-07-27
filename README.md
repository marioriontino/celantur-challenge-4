Performance Engineering &mdash; Image Processing Optimisation
==============================================================

Processing images fast and hardware-efficient is the core of our success.
Thus we want your help in improving our algorithms.
If you are solving this challenge as part of our *interview process*, please read [the detailed instruction](Hiring.md).  

***The goal of this challenge is to implement the fastest algorithm to blur the people (segmentation) in the images provided.***

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

The winner of [the monthly leaderboard](./Leaderboard.md) will be awarded a prize 🏆 in the form of an Amazon voucher. Further information will follow.

Don't hesitate to [write us](mailto:hello@celantur.com) if you have any questions concerning the challenge.

The Task
--------

You can download the images using [`download_coco_images.ipynb`](./download_coco_images.ipynb). Images are selected from the [COCO Dataset](https://cocodataset.org/#explore).

Implement the non-invertible blurring algorithm in a language of your choice, preferabbly C/C++ (CUDA) and/or Python. The COCO API provides [Python / Cython code](https://github.com/cocodataset/cocoapi/blob/8c9bcc3cf640524c4c20a9c40e89cb6a2f2fa0e9/PythonAPI/pycocotools/coco.py#L416) to turn the segmentation annotation 
into binary mask (numpy 2D array).

Provide us with information how to set up and run your code, preferrably Dockerised.

Share your code with the [Celantur Bot](https://github.com/celantor).

Evaluation
------------

The reference hardware on which the algorithm will be tested is a [p3.2xlarge](https://aws.amazon.com/ec2/instance-types/#Accelerated_Computing) with
- 1 NVIDIA Tesla V100 (16 GiB)
- 8 vCPUs: Intel Xeon Scalable Processor (Broadwell E5-2686 v4)
- 61 GiB Memory

The OS is **Linux** / Ubuntu 20.04 LTS (Focal Fossa). 

The blurring algorithm must be **irreversible** (a non-invertible function). 
