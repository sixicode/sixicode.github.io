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

<img src="">

This is a functionally equivalent representation of the vocal cords on which the intraglottal air
pressure acts. This model does not necessarily imply
such a distinct inner structure of the cords, corresponding one-to-one to the spring-coupled resonators.
Specifically, this coupled lumped-constant representation in the thickness (vertical) direction is a first-order
approximation of the distributed system of the vocal
cords, which vibrate with a vertical phase difference.
The glottis is approximated by thin rectangular crosssections and the masses are permitted lateral motion
only. z
For direct extension to the asymmetric cord model,
we restrict the asymmetric configuration of the pathological vocal cords such that both vocal cords are still
on the same level, and the upper and lower masses---
in the sense of the two-mass representationmwill colml2