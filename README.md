# GBAT: GazeBehavior Annotation Toolkit

GBAT is a toolkit for processing multimodal recordings of adult and children behavior. It has functions in extracting features from both egocentric and third-person video recordings. It includes three main components: a Video Synchronizer, a Gaze Target Annotator, and a Video Content Annotator.
![GBAT overview](d470d8ca4b61516d9350eb0c564bc63e.png)

Full Poster: [VSS_poster_86_40.pdf](https://github.com/user-attachments/files/28231453/VSS_poster_86_40.pdf)


## Why this toolkit exists

Children actively explore the world to learn its underlying causal structure. They use eye movements both to guide learning and to communicate intentions in social interactions. Head-mounted eye tracking enables researchers to study these gaze-based attentional processes in naturalistic behaviors. When combined with third-person audio and video recordings, such multimodal data also support analysis of the relationships among gaze targets, speech input, and body activity. However, these recordings are highly dense: children aged five to sixteen years make three to five saccades per second, and videos are typically recorded at tens of frames per second. This makes manual annotation of gaze targets and actions extremely labor-intensive. To facilitate the processing of multimodal recordings from egocentric and third-person videos, we developed the semi-automatic GazeBehavior Annotation Toolkit (GBAT).

This top-level repository groups the three component tools in one workspace:

- `Video_Synchronizer` for aligning recordings with audio-based synchronization
- `Sam2UI` for object segmentation and gaze-target annotation
- `Video-Annotator` for automated behavioral video annotation

## Repository Structure

### `Video_Synchronizer`
Tools for post-hoc synchronization of multi-camera video recordings, including egocentric and third-person views, using audio spectrogram correlation.

Top-level files:

- `extract_audios_1.py`
- `video_aligner_2.py`
- `gaze_frame_alignment&cut_3.py`

See [Video_Synchronizer/README.md](https://github.com/CaiLab-neuro/Video_Synchronizer.git).

### `Sam2UI` (Gaze_Target_Annotator)
Tools and UI for video object segmentation with semantic labels using SAM2/3 models. For egocentric videos, we also provide code to align eye-gaze data with segmented object masks to identify the semantic object category of each fixation (what object the person is looking at ?).

Top-level files:

- `install.py`
- `sam2_ui.py`
- `process_annotations.py`
- `process_gaze_mask_alignment.py`
- `segment.py`

See [Sam2UI/README.md](https://github.com/CaiLab-neuro/Sam2UI.git).

### `video_annotator`
Tools for video content annotation using a Vision-Language Model (VLM) in a question-answering framework. In human studies, this tool can be used to label human poses, behaviors, and environmental changes, such as whether a toy remains in the room.

Top-level files:

- `install.py`
- `annotate_video.py`
- `run_prompt_presets.py`
- `eaf_to_csv.py`
- `visualizer.py`

Supporting directories:

- `data`
- `profiles`
- `prompts`
- `scripts`
- `tarsier`

See [video-annotator/README.md](https://github.com/CaiLab-neuro/Video-Annotator).

## Suggested Workflow

1. Use `Video_Synchronizer` to align recordings.
2. Use `Sam2UI` to segment objects and support gaze-target annotation.
3. Use `Video-Annotator` to generate behavioral annotations from video segments.

## Installation

Each component has its own setup steps and dependencies. Install and run them from their respective directories using the instructions in their local READMEs.

## Citation

If you use GBAT, please cite:

```bibtex
@misc{baig2026gazebehaviorannotationtoolkitgbat,
  title={GazeBehavior Annotation Toolkit (GBAT): AI-powered toolkit for automatic annotation of egocentric eye-tracking and video data of child-caregiver interaction},
  author={Iba Baig and Kevin Li and Yanbin Xu and Seiji Cattelain and Marie Hallo and Hayato Ono and Sho Tsuji and Ming Bo Cai},
  year={2026},
  eprint={2605.22962},
  archivePrefix={arXiv},
  primaryClass={cs.CV},
  url={https://arxiv.org/abs/2605.22962}
}
```

## Contact

Yanbin Xu (yxx744@miami.edu)
Dr. Mingbo Cai (mingbo.cai@miami.edu)


