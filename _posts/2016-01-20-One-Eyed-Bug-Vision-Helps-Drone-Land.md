---
layout: post
title: "One-Eyed Bug Vision Helps Drone Land"
date: 2016-01-20 17:05:00
tags: [research]
comments: true
---

[IEEE Spectrum에 실린 Alexander Hellemans의 글](http://spectrum.ieee.org/automaton/robotics/aerial-robots/oneeyed-bug-vision-helps-drones-land)이다.

많은 연구자들은 더 작은 드론을 만들고 제어하기 위해서 곤충들이 어떻게 하는지 주의깊게 보고 있다. 대부분 곤충들의 비행은 optical flow라는, 눈에 보이는 물체들의 이동 속도에 기반하고 있는데 - 우리 사람들도 마찬가지로 많이 활용한다. 예를 들어, 우리가 운전 중일 때, 주위 차들의 속도는 단지 우리 시야에서 이 물체들이 얼마나 빨리 움직이는 지를 보고 판단해서, 운전 속도를 늦추거나 높이거나 한다.

이렇게보면 optical flow를 써서 제어하는 것이 쉬워보이지만, 드론의 경우는 좀 더 복잡하다. 왜냐하면, 앞뒤 뿐만 아니라 위아래까지 제어해야하는 3차원 영역이기 때문이다. 즉, 땅에서 어느정도 떨어져서 비행중인지 계속해서 인지하고 있어야 한다. 양안을 사용하는 stereo vision이라면 거리를 추측하는데 도움이 되겠지만, 아주 작은 드론처럼 센서 간 baseline이 극도로 작다면, 이 스테레오를 이용한 추측값은 부정확해질 수 밖에 없다.

그래서, 네덜란드 Delft University of Technology의 [Guido de Croon]는 하나의 카메라만을 사용해서, 이 때 얻는 optical flow에 의존하여 제어하는 드론 연구를 시작했다. 그는 이전에 European Space Agency에서 광학에 기반한 가벼운 보조 착륙 시스템을 개발했었다. 이러한 optical flow에 기반해서 착륙을 시도할 때, 그는 이상한 현상을 발견했는데 이 연구결과를 [Bioinspiration & Biomimetics]에 기고했다.

> 드론이 땅에 가까워지면, 어떤 지점에 이르러서 제어 시스템이 굉장히 불안해진다 - 진동하기 시작한다. 지면에서 발생하는 공기역학적인 문제가 아니라, 드론 그 자체가 진동을 시작한다.

De Croon은 이러한 현상을 초보 파일럿이 착륙하면서 비행 경로를 과도하게 조정하면서 위아래로 요동치는 현상과 비교해보았다. 활주로를 달려야하는 비행기의 경우에는 이러한 요동치는 현상은 착륙을 어렵게 만들지만, 지면에 수직으로 착륙하는 드론에 있어서는 오히려 보너스다.

"이런 진동은 지면으로부터 특정 거리에 다다를 때 발생합니다. 문제라고 볼 수 있지만, 어떻게보면 로봇에 있어 기회이기도 합니다. 왜냐하면, 진동이 발생하면 바로 이 지점이 **특정 거리만큼 떠있구나**하고 알 수 있으니까요." 이러한 현상은 곤충들의 비행에서도 주목할만한 특징이다. 벌의 경우에는 꽃에 앉기 전에 얼마정도 비행을 유지하는 호버링을 한다.

안전한 착지 뿐만 아니라, 이러한 진동은 특정 높이에서 드론을 제어하고 움직일 때도 활용할 수 있다. 진동을 일으키는 원이 되는 제어 이득(control gain)을 조절해가면서 특정 높이에서의 제어가 가능해진다. De Croon은 Control Gain을 특정 값으로 설정해서, 드론이 지면으로부터 일정 높이에 위치하면 진동하도록 만들었는데, 이 방법을 통해서 별다른 거리 센서가 없이도 - optical flow만으로 - 특정 높이를 유지할 수 있도록 제어할 수 있었다. 이러한 테크닉을 응용한다면, 장애물을 피하거나 수직이동 제어에도 유용하게 쓰일 것이다.

실험을 위해서 De Croon은 상용으로 널리 알려진 [Parrot AR Drone 2]를 사용했다. Drone에 설치된 카메라는 비행 시험용으로 사용되었고, 본래 드론에 장착되어 있던 높이 측정용 sonar sensor는 카메라를 통해 받은 결과가 맞는지 확인용으로 썼다. 해당 드론을 컨트롤 할 때에는 [Paparazzi open source autopilot]을 사용했다.

Optical-flow 계산은 하드웨어적, 소프트웨어적 요구량이 매우 적은 가벼운 알고리즘이다. g 단위의 무게를 가질 것으로 예상되는 미래의 곤충크기만한 드론은 이러한 기술의 응용이 필수적일 것이다.


[Guido de Croon]: http://www.bene-guido.eu/wordpress/
[Bioinspiration & Biomimetics]: http://iopscience.iop.org/article/10.1088/1748-3190/11/1/016004/meta
[Parrot AR Drone 2]: http://ardrone2.parrot.com/
[Paparazzi open source autopilot]: http://wiki.paparazziuav.org/wiki/
