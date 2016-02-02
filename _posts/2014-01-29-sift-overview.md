---
layout: post
title: "SIFT(Scale Invariant Feature Transform) Overview"
date: 2014-01-29 20:44:00
tags: [research]
comments: true
---

Object Recognition에서 가장 유명한 알고리즘을 꼽으라고 하면, SIFT를 빼놓을 수 없다. SIFT는 *Scale-Invariant Feature Transform*의 약자로, 1999년 ICCV(International Conference on Computer Vision)에서 처음으로 발표되었다. Object Recognition을 연구한 사람이라면 대부분 들어봤을 David Lowe의 대표작이다.

> D. G. Lowe, "Object Recognition from local scale-invariant features." International Conference on Computer Vision, Corfu, Greece (Sep. 1999), pp. 1150-1157.

이후에 특징점의 정확한 위치를 추정하는 Extrema localization 과정이 3D Interpolation 등이 추가되면서 개선된 버젼이 2004년에 저널로 정리되어 출판된다.

> D. G. Lowe, “Distinctive Image Features from Scale-Invariant Keypoints,” International Journal of Computer Vision, vol. 60, no. 2, pp. 91–110, Nov. 2004.

SIFT를 이해하기 위해서는 Scale-space Theory에 대한 이해부터 하고 넘어가야한다. Scale-invariant 한 특성(즉, 우리가 학습하는 물체가 실제 환경에서는 작게 나타나거나 더 크게 나타나더라도 동일한 물체로 인식할 수 있는 능력)은 Scale-space에서 나오기 때문이다. 이러한 Scale-space에 대해서는 다음에 다루도록 하고, 간단히 SIFT의 동작만을 정리해보면 아래와 같다.

1. **Scale-space extrema detection**: 국소적으로 튀는 부분을 찾는다. 결국 영상에서 특징적인 부분(도드라지게 나타나는 부분)을 찾는 것인데, 이후에 물체의 특징으로 표현된다.
2. **Keypoint Localization**: 앞서 찾은 특징들 중에서 아, 이건 정말 특징이 되겠구나하는 부분을 선별해내는 과정이다. 픽셀의 값(Intensity)을 보기도 하고, 위치나 크기(Edge는 너무 많이 추출되기 때문에 Corner에 대해서만 기술하는 편이 좋다. 이렇게 Edge 대신 Corner를 찾아가는 과정들도 포함)에 기반해서도 결정한다.
3. **Orientation Assignment**: SIFT의 특징 중 하나가, Orientation에 대해서도 불변하다는 것인데, 이 원리는 간단하다. 특징점 주변의 영역에 대해 Gradient를 구해서, 전체적으로 볼 때 픽셀들이 가리키는 방향을 구한다. 그리고 이 방향이 0도가 되도록 회전한다. 그리고 이렇게 회전한 부분영상에 대한 SIFT Descriptor를 Database에 저장한다. 이렇게 되면, 이후에 들어온 영상에서 물체가 90도 회전해있더라도, 최종적으로 특징점에서 패치가 SIFT형태로 기술될 때는 모두 같은 방향으로 회전한 상태이기 때문에, 같은(비슷한) 값을 가지는 SIFT Descriptor로 나타나게 된다.
4. **Keypoint Descriptor**: 앞선 과정에서와 같이 신중하게 Keypoint를 추출했다면, 그 내용을 기술해야한다. 이 때, SIFT에서는 특징점 주변의 Pixel값들을 그대로 기록하는 대신, 이 값들의 Orientation과 위치(특징점으로부터의 상대적인 위치값)에 기반한 Histogram으로 나타낸다. 일반적으로 SIFT에서 많이 사용하는 추천 Histogram Dimension은 128-dimension이다.
