---
license: apache-2.0
---

# What Lies Beneath: A Call for Distribution-based Visual Question & Answer Datasets

### Publication: TBD (linked on publication)
### GitHub Repo: TBD (linked on publication)

This is a histogram-based dataset for visual question and answer (VQA) with humans and large language/multimodal models (LMMs).

Data contains synthetically generated single-panel histograms images, data used to create histograms, bounding box data for titles, axis and tick labels, and data marks, and VQA question-answer pairs.  The subset of data presented in the paper (`example_hist/` folder) includes both human (two annotators) and LMM (ChatGPT-5-nano) annotations.

See GitHub link for code used to create and parse the following files.

## Directory Structure

Overview of the [directory structure](https://huggingface.co/datasets/ReadingTimeMachine/visual_qa_histograms/tree/main) is as follows:
 - `example_hists/` -- contains img and json for a small (80 images), visually uniform set of histogram data with several questions annotated by both LMMs
 - `example_hists_larger/` -- larger (500 images) dataset of uniform histogram images
 - `example_hists_complex/` -- largest (1000 images) dataset of histograms with a variety of distributions, shapes, colors, etc.

Paper-dataset (`example_hists/`) [directory structure](https://huggingface.co/datasets/ReadingTimeMachine/visual_qa_histograms/tree/main/example_hists):
 - `LLM_outputs/` -- contains outputs from various trials using ChatGPT-5
 - `imgs/` -- stores all images (also in `imgs.zip` file)
 - `jsons/` -- stores JSON for bounding boxes, data used to create images, VQA data
 - `human_and_llm_annotated_data.csv` -- contains two human annotations and two LMM annotations (gpt-5-nano, gpt-5-mini) for a subset of questions


## Human and LMM Annotations

Questions which have annotations in `human_and_llm_annotated_data.csv` are:
  1. "What is the median value of the data in this figure panel?" and, 
  2. "How many gaussians were used to generate the data for the plot in the figure panel?".  The addition of a constraint in the `format` part of the prompt of "Please choose an integer number from 1 to 5." was used in the LMM prompts to mimic the background knowledge of the human annotators.

Code for annotations from LMMs can be found in our GitHub repo linked at the top of this page.

Human annotations were performed with the [Zooniverse](https://www.zooniverse.org/) citizen science platform.  For the number of gaussians, the humans were prompted to enter a number:

<img src="https://huggingface.co/datasets/ReadingTimeMachine/visual_qa_histograms/resolve/main/docs/ngaussians.png" alt="Zooniverse interface showing histogram image with the prompt 'How many gaussians were used to make the underlying distribution?'">

For the median, humans are first prompted to input the median as a number:
<img src="https://huggingface.co/datasets/ReadingTimeMachine/visual_qa_histograms/resolve/main/docs/median_number.png" alt="Zooniverse interface showing histogram image with the prompt 'What is the median of the underlying distribution (as a number)?'">

The humans were then prompted to draw the median with a line tool:
<img src="https://huggingface.co/datasets/ReadingTimeMachine/visual_qa_histograms/resolve/main/docs/median_draw.png" alt="Zooniverse interface showing histogram image with the prompt 'What is the median of the underlying distribution (draw a line)?'">

The human-drawn annotations were found to be more accurate.



## Citation information

If you use this work please cite:
```
TBD
```