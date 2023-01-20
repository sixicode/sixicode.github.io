---
layout: post
title: Computer simulation of pathological vocal-cord vibration
author: sixicode
tags: [paper, simulation, physics, reh, incomplete]
---

<script type="text/x-mathjax-config">MathJax.Hub.Config({tex2jax:{inlineMath:[['\$','\$'],['\\(','\\)']],processEscapes:true},CommonHTML: {matchFontHeight:false}});</script>
<script type="text/javascript" async src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-MML-AM_CHTML"></script>


# Computer simulation of pathological vocal-cord vibration

## Memo

>DOI: 10.1121/1.381221<br><br>
>1976년도 논문이라 안 짚고 넘어가면 나중에 이해를 못할 것 같아서 정리해봄


## 용어 정리

영알못이라 모르는 단어가 좀 많음;;

<details>

vocal cord : 성대<br>

bilateral : 두 면을 가지거나 양면에 관한. 두 개의 측면을 갖는<br>

pathological : 병리학적인<br>

larynges(larynx의 복수형) : 후두<br>

glottal closure : closure of glottis(=middle part of the larynx)인듯<br>

dicrotic : Denoting a pulse in which a double beat is detectable for each beat of the heart<br>
- -crotic : having a heartbeat or pulse<br>

hoarse : 쉰<br>

devise : 고안<br>

thyroid cartilage : 방패연골<br>
> <details><summary>방패연골 사진</summary><center><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/8a/Larynx_external_en.svg/375px-Larynx_external_en.svg.png"></center></details><br>

resonators : 공명기

intra- : 안의 내부의

lumped circuit : 회로나 시스템전체가 하나의 point로 간주될 정도로 아주 작은 집합체로 되어있어 신호의 traveling time(전파시간)을 고려할 필요가 없는 것

lateral : 수평

deflection : 쳐짐, 편향, (스피링의 경우 눌려서 변형되는)

stiffness : 강성

excitation : 자극

aspiration : 호흡

</details>

## Abstract

성대의 dynamic model(a bilaterally symmetric two-mass model)은 a bilaterally asymmetric two-mass model로 확장되었다.

computer model의 비대칭적인 작동은 bilateral tension의 다양한 inbalance한 condition을 위해 만들어졌다.

이러한 computer model은 3종류의 basic vibratory mode를 보인다.

그리고 이 mode들은 tension imbalance가 있는 larynx에 대한 물리학 실험에서도 관찰된다.

1. cord vibration의 phase와 amplitude에 차이가 있는 다양한 vibration pattern
2. glottal closure 없는 거의 periodic mode
3. 불안정한 dicrotic, tricrotic motion

이 mode들은 subglottal pressure, glottal rest area와 cord parameter의 imbalance condition의 strong function(지배적인 parameter 느낌?)이다?

asymmetric vocal-cord model은 쉰 목소리를 simulate하기 위한 dynamic vocal-tract synthesizer로 통합되었다..

## Introduction

현실적인 움직임과 자연스러운 utterance의 생성을 토대로 symmetric two-mass model을 bilaterally asymmetric two-mass model로 확장시켰다.

이로서 behavior of the computer model under tension imbalance에 대한 연구와, model과 물리학적 결과의 비교가 가능하게 되었다.

이 model에서의 typical한 behavior에 대해 얘기하고자 한다.

## I. ASYMMETRIC MODEL OF THE VOCAL CORDS

two-mass model (Ishizaka and Matsudaira, 1968)에서, vocal cord는 스프링으로 연결된 2개의 mechanical resonators로 이루어져 있으며, 서로 대칭적이라 가정했다.

<center><img src="https://sixicode.github.io/assets/img/posts/2023-01-12-computer-simulation-of-pathological-vocal--cord-vibration/fig1.PNG"></center>

그리고 이는 vocal cord에 있어 intraglottal air pressure의 영향과 동일했다. 물론 이 model이 cord의 내부 구조와 동일하다는 뜻은 아니다.

특히, 이 coupled lumped-constant representation in the thickness (vertical) direction은 vocal cord의 (수직방향의 phase difference와 함께 진동하는) distributed system의 1차 근사이다.

glottis는 교차지점의 얇은 사각형으로 근사되었으며, masses( $m_{11},m_{12},m_{21},m_{22}$ )는 좌우로만 운동할 수 있다.

<center><img src="https://sixicode.github.io/assets/img/posts/2023-01-12-computer-simulation-of-pathological-vocal--cord-vibration/Fig2.PNG"></center>

direct extension을 위해서 both vocal cords는 그대로 same level에 두고 위쪽 mass와 아래쪽 mass가 opposing counterparts와'만' 충돌하도록 한다.

여기서의 충돌의 modeling은 asymmetrical model의 formulating에서 중요하다.

collision에서의 contact time을 구현하기 위해, 각 mass에 nonlinear spring을 추가한다.

그리고 그 spring은 deflection할 수록 equivalent stiffness가 커진다.

이 contact spring은 vocal cord의 flesh의 충돌 시 local deformation을 의미한다.

즉, Fig2(b)처럼 collision은 spring끼리의 deformation으로 표현한다.


또한, air pressure이 mass에 direct하게 작용한다고 가정하면,

collsion determination을 contact force의 계산없이 mass의 position만으로 할 수 있게 된다.

즉, Fig2(b)의 $x_{i2}-x_{i1} < 0 \; (i=1, 2) \quad where \quad x_{ij}:= (coordinate \; of \; m_{ij}) \; (j=1,2)$


Fig2(a)

> $\dot{x}$ 은 $m_{ij}$ 의 속도

> 스위치 $ Sw_i $ 는 $ m_{i1}, m_{i2} $ 가 충돌할 때 열린다

> $ Z_{hij} $ 는 contact spring의 mechanical impedance

> $ Z_{ij} $ 는 resonators의 mechanical impedance

> $ Z_{cj} $ 는 위아래 resonators들 간의 coupling impedance

> 4개의 generator $ F_{ij} $ 는 mass에 작용하는 공기역학적 힘

이 힘을 통해 mechanical system은 glottis 와 vocal tract의 fluid or acoustic system이 상호작용함.

synthesizer는 automatic noise sources for voiceless excitation를 포함함(Flanagan and Ishizaka (1976))
(voiceless excitation = glottal noise source)는 generates normal aspiration noise를 생성할 뿐 아니라 a noise component for breathy hoarse voices in pathological voice production를 제공한다.

$ \uparrow $ 여기 해석 이상할지도

원문
> The synthesizer includes automatic noise sources for voiceless excitation, as described in detail by Flanagan and
Ishizaka (1976), the glottal noise source of which not only generates normal aspiration noise but also provides a noise component for breathy hoarse voices in pathological voice production.

## II. BEHAVIOR OF THE ASYMMETRIC CORD MODEL
