# Technical Demos
This is a repository for a collection of technical demos made by Annotation-AI.

## Segment Everything: CPU acceleration and promptable applications
### Summary
Every demo doesn't use GPU resources, and they are served on CPU only instances.
- [Video](https://youtu.be/YLoCytavo-w)
- [Demo1 (Everything)](https://huggingface.co/spaces/Annotation-AI/fast-segment-everything) / [Demo2 (Text)](https://huggingface.co/spaces/Annotation-AI/fast-segment-everything-with-text-prompt) / [Demo3 (Image)](https://huggingface.co/spaces/Annotation-AI/fast-segment-everything-with-image-prompt) / [Demo4 (Drawing)](https://huggingface.co/spaces/Annotation-AI/fast-segment-everything-with-drawing-prompt) / [Demo5 (Click)](https://huggingface.co/spaces/Annotation-AI/segment-similarthings)

### Background
One of the most appealing applications of [Segment Anything Model (SAM)](https://segment-anything.com/) is *Everything*, which detects and segments all objects in an image.
However, it requires 1,024 inferences per a single image, and due to the reason, it is hard to be feasible for service providers who don’t have massive GPU resources.
In order to handle this issue, we re-implemented the Everything algorithm in iterative manner that is better for CPU only environments.
Mostly, we can expect comparable results to the original Everything within 1/5 number of inferences (e.g. 1024 vs 200), and it takes under 10 seconds to search for masks on a `CPU upgrade instance` (8 vCPU, 32GB RAM) of Huggingface space.

We named it `Fast Segment Everything`.
You can run the [DEMO](https://huggingface.co/spaces/Annotation-AI/fast-segment-everything) in HuggingFace Space.
![everything](https://github.com/annotation-ai/technical-demo/assets/14961526/7eb403bf-319a-41ae-815c-152fb279c25e)

### Applications: Promptable Segmentation
Based on `Fast Segment Everything` algorithm, we built a number of applications for promptable segmentation.: text, image, drawing, and click.

|Title|GIF|Demo|
|---|---|---|
|Segment everything with a text prompt|![everything_text](https://github.com/annotation-ai/technical-demo/assets/14961526/65d47323-0ceb-4881-9713-8c3f8c3ced0c)|[HuggingFace Space](https://huggingface.co/spaces/Annotation-AI/fast-segment-everything-with-text-prompt)|
|Segment everything with an image prompt|![everything_img](https://github.com/annotation-ai/technical-demo/assets/14961526/e5ef08b7-cb37-42bb-bb95-0298f0c2410e)|[HuggingFace Space](https://huggingface.co/spaces/Annotation-AI/fast-segment-everything-with-image-prompt)|
|Segment everything with a drawing prompt|![everything_drawing](https://github.com/annotation-ai/technical-demo/assets/14961526/0a10793d-9a35-4509-b667-9ccecfd3f737)|[HuggingFace Space](https://huggingface.co/spaces/Annotation-AI/fast-segment-everything-with-drawing-prompt)|
|Segment similar things! (Single click)|![similarthings](https://github.com/annotation-ai/technical-demo/assets/14961526/c7a04665-375e-4d37-8d5a-ee6b944d08a9)| [HuggingFace Space](https://huggingface.co/spaces/Annotation-AI/segment-similarthings)|
