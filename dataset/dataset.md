# 360World Dataset  
**A Curated Collection of 360° Video Clips for Research Use**

## Data Availability Statement
The 360World dataset is built exclusively from publicly accessible YouTube content; no proprietary or private sources are used. Instead of redistributing raw videos, we release only the YouTube video IDs required for download. This release is intended strictly for non-commercial research purposes and adheres to YouTube’s privacy and fair-use policies. No user-identifiable information is collected or disclosed.

## Clarifications
- Copyright of each video remains with the original uploader.  
- All content is sourced from the public Internet; our institutions claim no ownership and assume no responsibility for its meaning or legality.  
- By using this dataset, you agree not to reproduce, duplicate, sell, trade, or otherwise exploit any portion of the videos or derived data for commercial purposes. Further redistribution, publication, or mass distribution of the dataset is prohibited.

## Dataset Construction Pipeline

### 1. Data Collection & Filtering
- **Source**: Public YouTube videos.  
- **Search keywords**: “panorama”, “VR”, and related 360° terms.  
- **Filtering**: Manual review to ensure relevance, high resolution, and absence of policy violations.

### 2. Processing Workflow
- **Shot Segmentation**: Key frames are detected via inter-frame difference, after which the video is segmented into clips.
- **Text Annotation**: Each clip is captioned with ShareGPT4Video.  
- **Text Refinement**: Captions are summarized and polished by GPT-4.

## Dataset Overview
The 360World dataset consists of 7314 video clips curated from online 360 videos.
Each entry in `dataset/360video_data.csv` contains:

| Column         | Description                                                                 |
|----------------|------------------------------------------------------------------------------|
| YouTube_ID     | 11-character YouTube video ID. Full URL: `https://www.youtube.com/watch?v={id}` |
| Video_ID       | Composite identifier: `{YouTube_ID}_{clip_index}`                            |
| Caption        | Concise textual summary of the clip scene.                                   |
| Frame_Start    | First frame index (0-based) in the original video.                           |
| Frame_End      | Last frame index (inclusive) in the original video.                          |
| FPS            | Frame rate of the source video.                                              |
| Total_Duration | Duration (s) of the source video.                                            |
| Total_Frames   | Total frame count of the source video.                                       |

### Example Entry
| YouTube_ID | Video_ID       | Caption                                                                                          | Frame_Start | Frame_End | FPS | Total_Duration (s) | Total_Frames |
|------------|----------------|--------------------------------------------------------------------------------------------------|-------------|-----------|-----|---------------------|--------------|
| oovURIu4040 | oovURIu4040_7  | “A serene evening at an outdoor amphitheater. Attendees enjoy the sunset; shadows gradually lengthen.” | 3831        | 3987      | 30  | 258.4               | 7752         |

## License
360World is released under the [Creative Commons Attribution 4.0 International License (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).  
When using this dataset, please cite:  
```
@misc{zhou2025holotimetamingvideodiffusion,
      title={HoloTime: Taming Video Diffusion Models for Panoramic 4D Scene Generation}, 
      author={Haiyang Zhou and Wangbo Yu and Jiawen Guan and Xinhua Cheng and Yonghong Tian and Li Yuan},
      year={2025},
      eprint={2504.21650},
      archivePrefix={arXiv},
      primaryClass={cs.CV},
      url={https://arxiv.org/abs/2504.21650}, 
}
```
