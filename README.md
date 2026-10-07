# parking-space-detection
For my ITAI 1378 Computer Vision final project

## Project Tier
Tier 1: One model (YOLO), one job (find parking spaces and label each empty or occupied).

## Problem Statement
A full 17 hours per driver in a major U.S. city are estimated to be spent annually looking for parking.
Drivers and campus drivers may waste considerable time trying to find parking, which wastes fuel and can lead to significant frustration.
Campus parking office or lot owners may see many benefits of tackling this problem as well, as current solutions often rely on on-the-ground sensors
that are costly to install or detect lot availability through imprecise estimation.

## Solution Overview
The proposed model uses CCTV top-view footage in the parking area, identifies vehicles that are already parked in the parking slots and those vacant with the use of YOLOv8 model, then 
produces a labeled image that counts the available parking spots. With this, drivers and the managers may easily identify the number of vacant spots inside the premises at ease without the need to roam around.

## Technical Approach
- CV Technique: Object detection
- Model Architecture: CNN-based YOLO
- Model: YOLOv8 small (YOLOv8s)
- How we will use it: Transfer learning
- Framework: Ultralytics
- Why this approach: YOLOv8 is extremely efficient and simple to deploy on free Colab GPU's.
- In addition, it is also capable of handling a large number of small object detections within one frame.

## Dataset
- Source: PKLot
- Size: 12,416 images
- Labels: Bounding boxes with two classes, empty and occupied.
- Link: https://public.roboflow.com/object-detection/pklot

## Success Metrics (what we will measure and expect)
- Primary: mAP50 at least 0.90 on the test split.
- Secondary: Under 1 second per image.

## Milestone Plan
| Phase | Done when | 16-Week Term | 10-Week Term | What this looks like for my project |
|---|---|---|---|---|
| **Blueprint** | Proposal submitted and presented | Week 10 | Week 5 | Slides, GitHub repo, README, AI usage log started |
| **First Working Demo** | A pretrained model runs end to end on 5 to 10 sample images | Week 11 | Week 6 | Run pretrained YOLO on parking images in Colab, show the boxes, commit the notebook (this is your untouched fallback) |
| **Make It Yours** | System works on your problem with your data | Weeks 12 to 13 | Weeks 7 to 8 | Download PKLot dataset, sample about 3,000 images, fine-tune YOLO, save checkpoints to Drive, write the counting and output logic, take 30 to 50 own photos |
| **Improve and Measure** | Metrics recorded, failures understood | Week 14 | Week 9 | Measure mAP50, precision, recall, and speed on the test split, test on your own photos, collect failure cases, try one or two fixes (such as a different confidence threshold), measure again |
| **Build** | Final submitted | Week 15 | Week 10 | Demo video (3 to 5 minutes), updated README, final slides, finished AI usage log |

## Resources
- Compute: Colab / Kaggle
- Cost: $0, free tier or open source only

## Risks and Mitigation
| Risk | Probability | Plan B |
|---|---|---|
| The model works on the PKLot cameras but fails on a different lot or angle (domain shift) | High | Test on your own 30 to 50 photos and report the gap honestly. If the gap is large, label a small set of your own images in Roboflow and fine-tune lightly, or state clearly that the system is scoped to fixed-camera views like PKLot's. |
| Training fails, Colab disconnects, or data handling takes too long | Med | Save checkpoints to Google Drive and switch to Kaggle if needed. If training still fails, fall back to the pretrained model that counts cars, and put your effort into the application logic and evaluation. This matches the Project Guide's recovery plan. |

## Demo Video
[Link goes here at the Final]

## AI Usage Log
See docs/AI_usage_log.md

## Current Status
- [x] Repository created
- [ ] Proposal submitted
- [ ] First working demo
- [ ] System works on our data
- [ ] Metrics measured
- [ ] Final submitted
