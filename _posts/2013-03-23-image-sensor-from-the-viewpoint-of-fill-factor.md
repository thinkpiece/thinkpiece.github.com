---
layout: post
title:  "CMOS and CCD Image Sensor Sensitivities from Fill Factor"
date:   2013-03-23 04:11:00
tags: [research]
---

디지털 카메라가 발전된 역사를 보다보면, 예전에는 디지털 카메라 센서로 CCD가 사용되다가 어느 순간 CMOS로 대부분 전환되고 있음을 볼 수 있다. CCD로 얻은 사진이 보다 더 Film-like 한 색감을 얻을 수 있다고 주장하여 옛날 센서를 찾는 사람도 있지만, 대부분은 고감도의 이점 때문에 CMOS를 찾게 된다.

- CCD: CCD(Charge Coupled Device) 기술을 응용, 빛을 디지털 이미지로 변환하는 센서  
- CIS: CMOS Image Sensor의 약자. CMOS를 이용한 센서

 Image Sensor에는 Fill Factor라는 간단한 핵심 개념이 있는데, 이를 통해서 CCD와 CMOS 차이를 좀 더 논리적으로 알아볼 수 있다.

> **Fill Factor?** Percentage of a photosite. (sensitive to light) 즉, 빛을 감지하는 면적의 비율을 가리킨다. Fill Factor가 0.75라고 하면, 센서의 면적에서 75%가 빛을 받아들이는데 사용된다는 뜻. Fill Factor가 높을수록 같은 면적의 센서로 더 많은 빛을 받아들일 수 있기 때문에, 더 좋은 감도의 센서라 할 수 있다. 따라서 센서를 디자인하는 입장에서는 Fill Factor가 높도록 설계하는 것이 유리하다.

<figure>
<img src="http://cfile28.uf.tistory.com/image/177BC43E514CA9FF197FEA" />
<figcaption>An example of image sensor that has 0.75 fill factor.</figcaption>
</figure>

CCD와 CMOS는 그 원리 상 Fill Factor에 차이가 발생하게 되는데, 이 때문에 최종적으로 얻어지는 디지털 이미지에서도 두 센서 간에 차이가 발생하게 된다.

- CCD는 거의 100%에 가까운 Fill Factor를 가지고 있으나,
- CMOS는 그보다 낮은 Fill Factor를 가진다. 이는 photosite에서 얻은 전자를 CMOS에서 활용하기위해 전압으로 바꾸는 과정이 필요하기 때문.


Fill Factor가 낮다는 것은 (lower fill factor) Sensitivity가 낮다는 것이고 (less sensitive) 이는 더 긴 노출 시간을 필요로 한다. (long exposure time)

따라서, 일반적으로 CMOS는 CCD에 비해 광량이 충분하지 않은 상황(특히 실내 등)에서 퍼포먼스가 떨어진다. 하지만 CMOS는 VLSI 고집적화에 따라 대량 생산이 가능하기 때문에 비용상에 장점이 있고 전력 소모도 적다. 또한, CMOS를 이용하기 때문에, 별도의 CMOS IC가 없이 Sensor Chip 자체에서 추가적인 기능 구현이 가능하므로 최근의 다목적/다기능 센서로 개발되기에도 적합하다.


최근에는 센서단에서 간단한 모션감지, 외곽선검출 등을 수행하는 보다 복잡한 CMOS Image Sensor도 발표되고 있다.
