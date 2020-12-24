# Mid-Term Report

## Rubric

### Data Buffer

**Task MP.1 - The Data Buffer Optimization**

This was achieved by removing elements from the left while new ones are added from the right when the size of the _dataBuffer_ exceeds 2 elements. [Refer _MidTermProject_Camera_Student.cpp_ - Lines 62:69]

### Keypoints

**Task MP.2 - Keypoint Detection**

The HARRIS, FAST, BRISK, ORB, AKAZE, and SIFT detectors were implemented such that they are selectable by setting the _detectorType_ string accordingly. [Refer _MidTermProject_Camera_Student.cpp_ - Lines 82:97 and _matching2D_Student.cpp_ - Lines 143:259]

**Task MP.3 - Keypoint Removal**

Keypoints outside of a pre-defined rectangle are removed and only points within the rectangle are processed further [Refer _MidTermProject_Camera_Student.cpp_ - Lines 104:126].

### Descriptors

**Task MP.4 - Keypoint Descriptors**

The BRIEF, ORB, FREAK, AKAZE and SIFT descriptors were implemented such that they are selectable by setting the _descriptorType_ string accordingly. [Refer _MidTermProject_Camera_Student.cpp_ - Lines 154:156 and _matching2D_Student.cpp_ - Lines 57:100]

**Task MP.5 - Descriptor Matching**

FLANN matching and k-nearest neighbour selection were implemented such that they are selectable by setting the _selectorType_ string accordingly. [Refer _matching2D_Student.cpp_ - Lines 10:26]

**Task MP.6 - Desciptor Distance Ratio**

The K-Nearest-Neighbour matching was used to implement the descriptor distance ration test which looks at the ration of best vs. second best match to decide whether to keep an associated pair of keypoints. [Refer _MidTermProject_Camera_Student.cpp_ - Line 172 and _matching2D_Student.cpp_ - Lines 36:52]

### Performance

**Task MP.7 - Perfomance Evaluation 1**

The number of keypoints on the preceding vehicles for all 10 images were counted for all detectors implemented. [Refer _TASK----MP7.csv_]

**Task MP.8 - Performance Evaluation 2**

The number of matched keypoints for all 10 images were counted using all possible combinations of detectors and descriptors. In the matching step, the BF approach was used with the descriptor distance ratio set to 0.8. [Refer _TASK----MP8.csv_]

**Task MP.9 - Performance Evaluation 3**

The times taken for keypoint detection and descriptor extraction for all 10 images were counted using all possible combinations of detectors and descriptors. [Refer _TASK----MP9.csv_]

## Conclusion

**The TOP3  by Average Speed**

1. FAST/ORB - 4.4ms
2. FAST/BRIEF - 5.08ms
3. ORB/BRIEF - 9.59ms (with 60 matches)


**The TOP3 by Average Number of Matches**

1. FAST/BRIEF - 314 matches
2. FAST/ORB - 307 matches
3. FAST/FREAK - 248 matches (in 58.16ms)

**My TOP3**

1. FAST/ORB - 4.4ms (with 307 matches)
2. FAST/BRIEF - 5.08ms (with 314 matches)
3. ORB/BRIEF - 9.59ms (with 60 matches)

**Justification:**

It is true that the number of matches and time taken are of almost equal importance, so both were weighed in making the decision.
The first two seem almost interchangeably good, but time advantange of 0.6ms favors FAST/ORB over 7 extra matched points.
For the third place, SHITOMA/BRIEF with 104 matches in 20.8ms or ORB/BRIEF with 60 matches in 9.59ms were considered.
Once again, although ORB/BRIEF has fewer matches, it achieves that in half the time. 