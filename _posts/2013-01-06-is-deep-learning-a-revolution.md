---
layout: post
title: "Is Deep Learning a revolution or not?"
date: 2013-01-06 20:47:00
tags: [research]
comments: true
---

Deep Learning의 전신이 되는 Neural Network는 본래 1950년 후반에 소개된 역사있는 학문이다. Frank Rosenblatt는 이 당시에 뇌를 모방하는 Perceptron(퍼셉트론)이란 이름의 Neural Network를 제안했는데, 기본적인 삼각형과 사각형 형태 정도를 구분할 수 있었다. 반응은 폭발적이었다. 하지만 오래가진 못했다.

1969년에 Marvin Minsky가 저술한 책 때문이었다. Rosenblatt이 제안한 Perceptron은 기본적인 Exclusive-OR 연산도 수행하지 못하는 단점이 있었다. "사람의 뇌"를 닮았다고 한 시스템이 이런 기본적인 연산도 수행하지 못한다니? 그 이후로 Neural Networks는 급속도로 사장되었다.

1980년 중반이 되어서야 Neural Network는 다시 주목받는다. Carnegie-Mellon의 Geoff Hinton라는 젊은 교수가 Minsky가 지적한 단점을 보완하는 새로운 Neural Network 구조를 제안했기 때문이다. Hinton은 Perceptron에서 Hidden layer라고 불리는 Neuron Layer를 추가해서, 좀 더 복잡한 연산(예를 들어, Exclusive OR같은)을 하도록 만들었다. 이러한 새로운 형태의 Neural Network는 느리고 비효율적이지만, 확실히 동작하긴 했다. 다만, 처음의 Neural Network가 나올 때 사람들이 기대했던 “인공지능”과는 거리가 멀었고, 점점 사장되는 듯 했다.

하지만 2006년, NYU의 Yann LeCun의 연구에 기반한 Deep Learning이라는 새로운 형태의 Neural Network가 Hilton에 의해 소개된다. Deep Learning이 이전 연구와 차별되는 점이라면 Incremental Learning이 가능하다는 점을 들 수 있다. 예를 들어보자. 아이에게 처음 몇 개의 장난감을 가져다준다면, 처음에는 색깔별로, 그리고 크기별로, 기능별로, 또는 다른 특징에 의거해서 무의식 중에 구분(categorize)할 것이다. 마찬가지로 Deep Learning에서는 수많은 데이터를 각각의 Low-level feature에 따라 구분한 뒤(Low-level categories), 좀 더 높은 수준의 분류(High-level categories)를 하는 방식이다.

그리고 이러한 방식은 Google이 자신들의 시스템에 활용하면서 그 성능이 더욱 주목받게 되었다. 다만, 인공 지능을 구했다는 식의 성능을 보여주는 것은 아니다. 여전히 몇 개 수준의 물체를 구분하는 데에 그치고 있으며, 회전이나 크기 변화 등에도 성능 저하가 심각하다고 한다.

물론, 이러한 상황을 "Deep Learning으로 인공지능을 구현하기 어렵다"고 받아들이는 것은 옳지않다. Deep Learning은 인공 지능 머신을 구현하는 데에 있어 일부로 생각하는 편이 낫다. 아직까지 많은 경우에 있어서, 인공지능 알고리즘은 인과 관계를 학습한다기 보다는 "~는 ~다."" 수준의 동의관계를 학습하는 방식이지만 딱히 대안이 없기도 하다. 예전에 Jeopardy라는 미국 TV쇼에 나온 IBM의 Watson이라는 인공지능 컴퓨터는 이 게임에서 이기기 위해서, 다양한 머신 러닝 알고리즘을 접합한 방식으로 개발되어 막대한 상금을 타간 적도 있다.

이러한 Deep Learning의 발전은 우리가 꿈꾸는 인공 지능의 시대를 앞당겨줄까? 마치 소설책을 읽고 스토리를 이해하는 로봇의 출현같은 거 말이다. Hilton의 Deep Learning이 인공 지능에 기여한 바를 아래와 같이 한 문장을 정리하면서 대신하고자 한다.

> Hilton has built a better ladder; but a better ladder doesn’t necessarily get you to the moon.

출처: [IS “DEEP LEARNING” A REVOLUTION IN ARTIFICIAL INTELLIGENCE?](http://www.newyorker.com/online/blogs/newsdesk/2012/11/is-deep-learning-a-revolution-in-artificial-intelligence.html) posted by Gary Marcus from The New Yoker
