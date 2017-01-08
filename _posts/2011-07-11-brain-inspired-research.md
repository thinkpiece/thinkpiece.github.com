---
layout: post
title: "Brain-inspired Research and Memristor"
date: 2011-07-11 23:40:00
tags: [research]
comments: true
---

프로세서를 설계하는 사람들은 여러 각도로 성능을 끌어올리기 위해 노력해왔다. 동작 속도를 빠르게하거나 (펜티엄4 까지) 코어 개수를 늘리거나 (최근까지) 하는 것들이 그런 노력이다. 하지만, 흔히 폰 노이만 아키텍쳐(von Neumann Architecture)라고 불리는 기존 컴퓨터 구조의 한계가 드러나면서 성능 향상은 정체되고, **발상의 전환**이 필요한 때가 아닌가, 하는 이야기가 여기저기서 나오고 있는 상황이다.


IEEE SPECTRUM DECEMBER 2010에 게재되었던 [Meet MoNETA-the brain-inspired chip that will outsmart us all](https://cs.uwaterloo.ca/~brecht/courses/854-Emerging-2014/readings/memristors/The_brain_of_new_machine.pdf) 도 이러한 분위기에서 연구되고 있는 주제다.


MoNETA란 **Modular Neural Exploring Traveling Agent**의 약자로써, Boston University의 Department of cognitive and neural systems에서 제작한 소프트웨어를 California HP Lab의 bio-inspired microprocessor에서 동작시킨 프로젝트로, 뇌를 모방한 하드웨어 구조를 구현하여 이를 **소프트웨어**까지 구동할 수 있다는, 기존 컴퓨터의 전과정을 수행했다는 데에 의의가 있다.


그렇다면 어떻게 설계해야 뇌를 모방했다고 할 수 있나? 이 연구에서는 Bio-inspired microprocessor의 가장 큰 특징은 바로 memristor를 이용하여 제작되었다는 것인데, memristor는 Bio-inspired 소자로써 기존의 Transistor를 훗날 대체할 수 있다는 기대를 받고 있다.[^1]


기존에도 일종의 **지능형**이라는 수식어가 붙는 서비스들이 많은데, 기존의 인공지능 서비스들, 예를 들어 Gmail의 Priority Inbox 등은 상당히 똑똑하게 동작하긴 하지만 그렇다고해서 **지능을 가졌다**고는 할 수 없다. 그저 특정 작업에 대해 지능적으로 프로그램 되었을 뿐이다. 예상하지 못한 환경에 놓이더라도 처음부터 규칙을 찾아내고 지능적인 결론을 내리는 것까지 알아서 할 수 있어야 **지능을 가졌다**라고 할 수 있지 않을까?


물론 어떻게 가능할지는 모른다. 1997년 IBM에는 무게만 해도 1.4톤에 이르는 DeepBlue라는 Supercomputer 프로젝트가 있었는데, 당시 체스 세계챔피언이던 Kasparov를 이겼지만 우리가 지능을 가졌다라고는 하지 않는다. 1초당 2억번이 넘는 체스 움직임을 계산하여 다음 수를 선택하는 단순한 Brute-force strategy로는 체스를 잘할 순 있지만 사람과 대화를 잘한다거나, 창의적인 그림을 잘 그린다거나 할 수는 없다.


이 후에도 많은 **지능 프로젝트**들이 진행되었고, 진행되고 있지만 DeepBlue와 크게 다르지 않은 성격이다. 새로운 상황에 대해 대처할 수 있는 법을 스스로 깨닫는 지능이라기보다는, 인간의 특정 행동을 보조하고자 하는 목적에서, 어느정도의 정의되지 않은 상황이 발생하더라도 좋은 판단을 내릴 수 있는 제한된 범위의 지능 연구가 활발하다.
DARPA에서 진행하는 Grand Challenge에서는[^2] 인간이 사전에 정의한 대로만 움직이는 fixed algorithm에 비해 어느정도 컴퓨터가 판단할 수 있게 한 인공 지능 알고리즘이 더 좋은 성과를 거두는 등, 인공지능 연구의 미래를 엿볼 수 있는 사건들이 이어지고 있다. 차후에 신호 체계가 있는 도심에서도 유연하게 동작하는 인공지능 자동차가 출현한다면 더 실감될 것이다.


한편으로는, 이렇게 **기능적으로 뇌를 모방하는** 움직임의 반대편에서 **구조적으로 뇌를 모방하는** 연구도 활발히 진행되고 있다. 기능적으로 뇌를 모방하는 연구가 활발히 진행될 수록 기존 컴퓨터 구조에서 요구되는 연산량, 메모리량이 기하급수적으로 늘고 있기 때문이다. 하지만 컴퓨터 성능의 정체는 이미 멀티코어 프로세서 시대에 이르러 일반인까지 체험하는 수준에 이르렀다. 이러한 상황에서 컴퓨터 구조에서도 생명체, 사람의 프로세서에 해당하는 뇌를 모방해서 해답을 찾아보자는 연구가 진행되기 시작했고, memristor는 마침 이러한 분위기와 그 동작 특성이 맞물리면서 각광받기 시작한다.


Memristor에 관련한 많은 논문들이 그저 **모든 해결책은 memristor로 넘어가라**고만 하고 있어서 영양가 없는 논문도 많이 나오고 있는 상황이지만 이들이 일간되게 주장하는 메모리, 그리고 연산의 통합적인 아키텍쳐가 필요하다는 주장은 귀기울일만 하다.

> Change your architecture to merge memory and computation!


[^1]: 생명체의 기본 단위인 뉴런의 통신방식은 시냅스의 전하량 축적으로 일어나는데, 전하량을 기억하는 Memristor의 동작이 이와 닮았다.
[^2]: California 사막을 횡단하는 무인자동차 대회이다.
