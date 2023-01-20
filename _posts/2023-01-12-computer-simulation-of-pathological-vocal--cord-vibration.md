---
layout: post
title: Computer simulation of pathological vocal-cord vibration
author: sixicode
tags: [paper, simulation, physics, reh, incomplete]
---

# Computer simulation of pathological vocal-cord vibration

DOI: 10.1121/1.381221

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
> <details><summary>방패연골 사진</summary><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/8a/Larynx_external_en.svg/375px-Larynx_external_en.svg.png"></details><br>

resonators : 공명기

intra- : 안의 내부의

lumped circuit : 회로나 시스템전체가 하나의 point로 간주될 정도로 아주 작은 집합체로 되어있어 신호의 traveling time(전파시간)을 고려할 필요가 없는 것

lateral : 수평

</details>

## Abstract

성대의 dynamic model(a bilaterally symmetric two-mass model)은 a bilaterally asymmetric two-mass model로 확장되었다. computer model의 비대칭적인 작동은 bilateral tension의 다양한 inbalance한 condition을 위해 만들어졌다. 이러한 computer model은 3종류의 basic vibratory mode를 보인다. 그리고 이 mode들은 tension imbalance가 있는 larynx에 대한 물리학 실험에서도 관찰된다.
1. cord vibration의 phase와 amplitude에 차이가 있는 다양한 vibration pattern
2. glottal closure 없는 거의 periodic mode
3. 불안정한 dicrotic, tricrotic motion

이  mode들은 subglottal pressure, glottal rest area와 cord parameter의 imbalance condition의 strong function(지배적인 parameter 느낌?)이다?

asymmetric vocal-cord model은 쉰 목소리를 simulate하기 위한 dynamic vocal-tract synthesizer로 통합되었다..

## Introduction

현실적인 움직임과 자연스러운 utterance의 생성을 토대로 symmetric two-mass model을 bilaterally asymmetric two-mass model로 확장시켰다.
이로서 behavior of the computer model under tension imbalance에 대한 연구와, model과 물리학적 결과의 비교가 가능하게 되었다.
이 model에서의 typical한 behavior에 대해 얘기하고자 한다.

## I. ASYMMETRIC MODEL OF THE VOCAL CORDS

two-mass model (Ishizaka and Matsudaira, 1968)에서, vocal cord는 스프링으로 연결된 2개의 mechanical resonators로 이루어져 있으며, 서로 대칭적이라 가정했다.

<img rc="https://sixicode.github.io/assets/img/posts/2023-01-12-computer-simulation-of-pathological-vocal--cord-vibration/fig1.PNG">

그리고 이는 vocal cord에 있어 intraglottal air pressure의 영향과 동일했다. 물론 이 model이 cord의 내부 구조와 동일하다는 뜻은 아니다.
특히, 이 coupled lumped-constant representation in the thickness (vertical) direction은 vocal cord의 (수직방향의 phase difference와 함께 진동하는) distributed system의 1차 근사이다.
glottis는 교차지점의 얇은 사각형으로 근사되었으며, masses( $m_{11}, m_{12}, m_{21}, m_{22}$ )는 좌우로만 운동할 수 있다.

direct extension을 위해서 both vocal cords는 그대로 same level에 두고 위쪽 mass와 아래쪽 mass가 opposing counterparts와'만' 충돌하도록 한다.

여기서의 충돌의 modeling은 asymmetrical model의 formulating에서 중요하다.
collision에서의 contact time을 구현하기 위해, 각 mass에 추가적인 nonlinear spring을 

z
For direct extension to the asymmetric cord model,
we restrict the asymmetric configuration of the pathological vocal cords such that both vocal cords are still
on the same level, and the upper and lower masses---
in the sense of the two-mass representationmwill colml2