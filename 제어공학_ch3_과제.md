{
  "nbformat": 4,
  "nbformat_minor": 0,
  "metadata": {
    "colab": {
      "provenance": [],
      "authorship_tag": "ABX9TyPQ5H0VHje28cPLIFC6Zbo5",
      "include_colab_link": true
    },
    "kernelspec": {
      "name": "python3",
      "display_name": "Python 3"
    },
    "language_info": {
      "name": "python"
    }
  },
  "cells": [
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "view-in-github",
        "colab_type": "text"
      },
      "source": [
        "<a href=\"https://colab.research.google.com/github/omingyun/control-engineering/blob/main/%EC%A0%9C%EC%96%B4%EA%B3%B5%ED%95%99_ch3_%EA%B3%BC%EC%A0%9C.md\" target=\"_parent\"><img src=\"https://colab.research.google.com/assets/colab-badge.svg\" alt=\"Open In Colab\"/></a>"
      ]
    },
    {
      "cell_type": "markdown",
      "source": [
        "# 제어공학 챕터3 과제\n",
        "#### 2018732022 오민균\n",
        "---\n",
        "## P 3.1\n",
        "스프링-질량-감쇠기의 운동방정식은 다음과 같다.  \n",
        "$$ M{d^2y(t) \\over dt^2}+b{dy(t) \\over dt}+ky(t) = F(t) $$  \n",
        "(a) 적당한 상태변수 $x_{1}(t)$와 $x_{2}(t)$ 를 각각 ${dy(t) \\over dt},{y(t)}$로 설정한다.   \n",
        "(b) 상태변수를 통해 운동방정식을 아래와 같은 1차 미분방정식으로 포현할 수 있다.  \n",
        "$$ {dx_{1}(t) \\over dt} = -{b \\over M}x_{1}(t)-{k \\over M}x_{2}(t)+{F(t) \\over M} $$  \n",
        "$$ {dx_{2}(t) \\over dt} = x_{1}(t) $$  \n",
        "$$ y(t) = x_{2}(t) $$  \n",
        "(c) $ x(t)={x_{1}(t) \\brack x_{2}(t)} $ 라고 할 때, $ {dx_{1}(t) \\over dt} $ 과 $ {dx_{2}(t) \\over dt} $ 에 관한 식을 행렬로 표현하면 상태미분방정식이 된다.  \n",
        "$$ \\begin{bmatrix}\\dot{x_{1}(t)} \\\\ \\dot{x_{2}(t)} \\end{bmatrix} = \\begin{bmatrix}-{b \\over M}&-{k \\over M}\\\\1&0\\\\ \\end{bmatrix}x(t)+ \\begin{bmatrix}{1 \\over M}\\\\0\\\\ \\end{bmatrix}F(t) $$  \n",
        "---  \n",
        "## P 3.3  \n",
        "### KVL  \n",
        "KVL을 이용하면 $x_{1}(t)$에 관한 미분방정식을 얻을 수 있다.  \n",
        "$$ {di_{L}(t) \\over dt} = {v_{C}(t) \\over L} - {v_{2}(t) \\over L} + {v_{1}(t) \\over L} $$\n",
        "### KCL  \n",
        "KCL을 이용하면 $x_{2}(t)$에 관한 미분방정식을 얻을 수 있다.  \n",
        "$$ {dv_{C}(t) \\over dt} = -{i_{L}(t) \\over C} + {v_{2}(t) \\over RC} - {v_{C}(t) \\over RC} $$  \n",
        "이를 행렬로 표현하면 상태미분방정식을 구할 수 있다.  \n",
        "$$ \\begin{bmatrix}\\dot{x_{1}(t)} \\\\ \\dot{x_{2}(t)} \\end{bmatrix} = \\begin{bmatrix}0&{1 \\over L}\\\\-{1 \\over C}&-{1 \\over RC}\\\\ \\end{bmatrix}\\begin{bmatrix}x_{1}(t)\\\\x_{2}(t)\\\\ \\end{bmatrix} + \\begin{bmatrix}{1 \\over L}&-{1 \\over L}\\\\0&{1 \\over RC}\\\\ \\end{bmatrix}\\begin{bmatrix}v_{1}(t)\\\\v_{2}(t)\\\\ \\end{bmatrix} $$  \n",
        "---\n",
        "## P 3.5  \n",
        "그림 3.5에 주어진 블록선도를 통해 전달함수를 구할 수 있다.  \n",
        "$$ Y(s) = [R(s)-Y(s)]·{s+2 \\over s+8}·{1 \\over s-3}·{1 \\over s} $$  \n",
        "$$ [1+({s+2 \\over s+8}·{1 \\over s-3}·{1 \\over s})]Y(s) = R(s)·{s+2 \\over s+8}·{1 \\over s-3}·{1 \\over s} $$  \n",
        "$$ {Y(s) \\over R(s)} = {s+2 \\over s^3+5s^2-23s+2} $$\n",
        "$$ ∴ T(s) = {s+2 \\over s^3+5s^2-23s+2} $$  \n",
        "---\n",
        "## P 3.12  \n",
        "주어진 전달함수의 분자분모에 각각 Z(s)를 곱한 후, Y(s)와R(s)를 라플라스 역변환을 시켜주면 다음과 같은 미분방정식이 나온다.  \n",
        "$$y(t) = 8{dz(t) \\over dt} + 5z(t) $$  \n",
        "$$r(t) = {d^3z(t) \\over dt^3} + 12{d^2z(t) \\over dt^2} + 44{dz(t) \\over dt} + 48z(t) $$  \n",
        "이때, 상태변수x1,x2,x3를 다음과 같이 정하면  \n",
        "$$ x_{1}(t)=z(t) $$  \n",
        "$$ x_{2}(t)={dz(t) \\over dt} $$  \n",
        "$$ x_{3}(t)={d^2z(t) \\over dt^2} $$  \n",
        "$ \\dot{x_{3}}(t) $는 $ {d^3z(t) \\over dt^3} $와 같다. 따라서\n",
        "$$ \\dot{x_{3}}(t)=r(t)-12x_{3}(t)-44x_{2}(t)-48x_{1}(t) $$\n",
        "이므로 행렬로 나타내면 다음과 같이 표현할 수 있다.  \n",
        "$$ \\dot{x(t)} = \\begin{bmatrix} 0&1&0\\\\0&0&1\\\\-48&-44&-12 \\end{bmatrix}x(t)+\\begin{bmatrix} 0\\\\0\\\\1 \\end{bmatrix}r(t) $$  \n",
        "$$ y(t) = \\begin{bmatrix} 40&5&0 \\end{bmatrix}x(t) $$  \n",
        "여기서 $A = \\begin{bmatrix} 0&1&0\\\\0&0&1\\\\-48&-44&-12 \\end{bmatrix}$ 이므로 상태천이행렬을 구하기 위해 $(sI-A)^{-1} $ 을 계산하면 아래와 같다.  \n",
        "$$ Φ(s) = \\begin{bmatrix}{1 \\over s}&{1 \\over s^2}&0\\\\0&{1 \\over s}&0\\\\-{48 \\over s(s+12)}&-{4(11s+12) \\over s^2(s+12)}&{1 \\over s+12} \\end{bmatrix}$$  \n",
        "이를 다시 라플라스 역변환을 취해주면 상태천이행렬이 된다.  \n",
        "$$ ∴Φ(t) = \\begin{bmatrix}1&t&0\\\\0&1&0\\\\4e^{-12t}-4&{10 \\over 3}e^{-12t}-4t-{10 \\over 3}&e^{-12t} \\end{bmatrix} $$  \n",
        "---\n",
        "## P 3.17  \n",
        "상태변수 방정식에서 전달함수를 구하는 식은 다음과 같다.  \n",
        "$$ G(s) = {Y(s) \\over U(s)} = CΦ(s)B+D $$\n",
        "따라서 전달함수를 구하기 위해서는 $C,Φ(s),B,D$가 필요하다. $C,B,D$는 문제에 주어져 있는대로 각각 다음과 같다.$$ B = \\begin{bmatrix}0\\\\0\\\\4 \\end{bmatrix} , C = \\begin{bmatrix}1&0&0\\end{bmatrix} , D=0 $$  \n",
        "$A = \\begin{bmatrix}1&1&-1\\\\4&3&0\\\\-2&1&10 \\end{bmatrix}$ 이므로 $Φ(s)$를 구하기 위해 $(sI-A)^{-1}$을 계산하면 다음과 같다.\n",
        "$$ (sI-A)^{-1} = Φ(s) = {1 \\over s^3-14s^2+37s+20}\\begin{bmatrix}(s-3)(s-10)&s-11&-s+3\\\\4(s-10)&s^2-11s+8&-4\\\\-2(s-5)&s-3&s^2-4s-1 \\end{bmatrix} $$  \n",
        "위에서 구한 $ Φ(s) $에 $B,C$를 곱해주면 전달함수를 구할 수 있다.\n",
        "$$ ∴G(s) = {Y(s) \\over U(s)} = CΦ(s)B = {-4s+12 \\over s^3-14s^2+37s+20} $$"
      ],
      "metadata": {
        "id": "EaNkka_2JYWP"
      }
    }
  ]
}