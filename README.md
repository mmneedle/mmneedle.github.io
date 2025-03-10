# Multimodal Needle in a Haystack (MMNeedle)

**Multimodal Needle in a Haystack: Benchmarking Long-Context Capability of Multimodal LLMs**<br>
H. Wang, H. Shi, S. Tan, W. Qin, W. Wang, T. Zhang, A. Nambi, T. Ganu, H. Wang<br>
*Annual Conference of the North American Chapter of the Association for Computational Linguistics (NAACL), 2025.*<br>
[[Paper](https://arxiv.org/pdf/2406.11230)] [[MMNeedle Dataset](https://drive.google.com/drive/folders/1D2XHmj466e7WA4aY7zLkbdTmp3it2ZPy?usp=sharing)]

To use this benchmark, please download the MMNeedle dataset at this [link](https://drive.google.com/drive/folders/1D2XHmj466e7WA4aY7zLkbdTmp3it2ZPy?usp=sharing). Alternatively, you could also construct your version of MMNeedle by following the [instructions](https://github.com/Wang-ML-Lab/multimodal-needle-in-a-haystack). 

## News
(2025-03-07) MMNeedle is selected for an **Oral Presentation** at NAACL!

(2025-02-08) Multimodal Needle in a Haystack (MMNeedle) was accepted at **NAACL 2025** Main! Additional models coming soon.

(2024-06-24) We released the *leaderboard* for Multimodal Long Context Understanding on [Paper with Code](https://paperswithcode.com/sota/long-context-understanding-on-mmneedle)!

(2024-06-17) We released the [paper, code, and data](https://github.com/Wang-ML-Lab/multimodal-needle-in-a-haystack) for Multimodal Needle in a Haystack (MMNeedle) benchmark!

## Overview
<img width="1000" alt="Screen Shot 2024-06-17 at 7 38 45 PM" src="https://github.com/Wang-ML-Lab/multimodal-needle-in-a-haystack/assets/30172609/cf481db4-ac83-4940-8897-e27d4faab4a8">

**MMNeedle Evaluation Overview.** Correct answers are marked with *checkmark* ($\checkmark$), while the incorrect answers are marked with <span style="color: red;">*cross* ($\times$)</span>. Our evaluation setup involves the following key components:
**(a) Needle Sub-Image:** The needle sub-image to be retrieved based on the given caption.
**(b) Haystack Image Inputs:** The long-context visual inputs consist of M images, each stitched from <span style="color: red;">N $\times$ N</span> sub-images.
**(c) Text Inputs (Instructions and Caption):** Detailed instructions to MLLMs, followed by a <span style="color: green;">caption</span> describing the needle, i.e., <span style="color: green;">sub-image 20</span>.
**(d) LLM Outputs:** The answers from different MLLMs, indicating their ability to accurately locate the needle in the haystack based on the given caption. The expected output is composed of the model's identification of the index, row, and column of the matching sub-image. The results showcase the comparative performance of various models: GPT-4o correctly predicts the exact location of the needle; Gemini Pro 1.5 only correctly predicts the image index of the needle; other API models predict incorrect locations; open-source models often output with wrong formats.

<img width="1000" alt="Screen Shot 2024-06-17 at 7 39 52 PM" src="https://github.com/Wang-ML-Lab/multimodal-needle-in-a-haystack/assets/30172609/e105e2f6-0585-4cbc-9e56-0f588134412d">

**MMNeedle Evaluation Performance Comparison (Claude-3 refers to Claude 3 Opus, and Gemini-1.0/1.5 refers to Gemini Pro 1.0/1.5).** The x-axis shows the results of different models, and the y-axis shows the results on various input image number M and stitching size N. For each row, i.e., setting (M,N), we show the average accuracy (%) of each model. For each stitched image, the color of row r, column c indicates the accuracy of predicting the exact position for samples with the "needle" sub-image in position (r,c) of the stitched image. For the M=10 setting, we show the average accuracy of each location (r,c) over 10 images. A <span style="color: red;"><em>redder</em></span> cell indicates lower accuracy, while a <span style="color: green;"><em>greener</em></span> cell indicates higher accuracy. The best result for each row is marked with <underline>underlining</underline>.
