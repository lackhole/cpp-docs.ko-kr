---
title: 전처리기 문법
ms.date: 08/29/2019
helpviewer_keywords:
- preprocessor
- grammar, preprocessor
- preprocessor, grammar
ms.assetid: 6cd33fad-0b08-4592-9be8-7359c43e24e9
ms.openlocfilehash: f0916e3cc9bbdb398db693286dacc4517df03557
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222267"
---
# <a name="preprocessor-grammar"></a>전처리기 문법

*제어 줄*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#define** *식별자* *토큰 문자열* <sub>opt</sub>\
&nbsp;&nbsp;&nbsp;&nbsp; **#define** *식별자* **(** &#x2800;식별자&#x200B;<sub>옵트인</sub> **,** ... **,** *식별자* &#x200B; <sub></sub>opt&#x2800; **)** *토큰 문자열*<sub>옵트인</sub>\
&nbsp;&nbsp;&nbsp;&nbsp; **#include** **"** _경로-사양_ **"** \
&nbsp;&nbsp;&nbsp;&nbsp; **#include** _경로-사양_ **\<** **>** \
&nbsp;&nbsp;&nbsp;&nbsp; **#line** *숫자 시퀀스* **"** _파일 이름_ **"** &#x200B; <sub>opt</sub>  \
&nbsp;&nbsp;&nbsp;&nbsp; **#undef** *식별자*\
&nbsp;&nbsp;&nbsp;&nbsp; **#error** *토큰 문자열*\
&nbsp;&nbsp;&nbsp;&nbsp; **#pragma** *token-string*

*상수-식*: \
&nbsp;&nbsp;&nbsp;&nbsp;**정의 됨 (** &#x2800;*식별자*&#x2800; **)** \
&nbsp;&nbsp;&nbsp;&nbsp;**정의 됨** *식별자*\
&nbsp;&nbsp;&nbsp;&nbsp;기타 상수 식

*조건*: \
&nbsp;&nbsp;&nbsp;&nbsp;*if-part* *elif-parts*<sub>opt</sub> *else-part*<sub>opt</sub> *endif-line*

*-part*: \
&nbsp;&nbsp;&nbsp;&nbsp;*if-line* *text*

*if-line*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#if** *상수 식*\
&nbsp;&nbsp;&nbsp;&nbsp; **#ifdef** *식별자*\
&nbsp;&nbsp;&nbsp;&nbsp; **#ifndef** *identifier*

*elif-파트*: \
&nbsp;&nbsp;&nbsp;&nbsp;*elif-줄* *텍스트*\
&nbsp;&nbsp;&nbsp;&nbsp;*elif-parts* *elif-line* *text*

*elif 줄*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#elif** *constant-expression*

*else-파트*: \
&nbsp;&nbsp;&nbsp;&nbsp;*else-line* *text*

*else 줄*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#else**

*endif-줄*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#endif**

*숫자 시퀀스*: \
&nbsp;&nbsp;&nbsp;&nbsp;*분모*\
&nbsp;&nbsp;&nbsp;&nbsp;*digit-sequence* *digit*

*digit*: \ 중 하나
&nbsp;&nbsp;&nbsp;&nbsp;**0 1 2 3 4 5 6 7 8 9**

*토큰 문자열*: \
&nbsp;&nbsp;&nbsp;&nbsp;토큰 문자열

*토큰*: \
&nbsp;&nbsp;&nbsp;&nbsp;*키워드로*\
&nbsp;&nbsp;&nbsp;&nbsp;*한정자*\
&nbsp;&nbsp;&nbsp;&nbsp;*상시*\
&nbsp;&nbsp;&nbsp;&nbsp;*연산자*\
&nbsp;&nbsp;&nbsp;&nbsp;*punctuator*

*파일 이름*: \
&nbsp;&nbsp;&nbsp;&nbsp;법적 운영 체제 파일 이름

*경로-사양*: \
&nbsp;&nbsp;&nbsp;&nbsp;Legal file path

*텍스트*: \
&nbsp;&nbsp;&nbsp;&nbsp;모든 텍스트 시퀀스

> [!NOTE]
> 다음 비 터미널은  *C++ 언어 참조*의 [어휘 규칙](../cpp/lexical-conventions.md) 섹션에서 확장 됩니다. *상수*, *상수 식*, *식별자*, *키워드*, *연산자*및  *punctuator*.

## <a name="see-also"></a>참고자료

[문법 요약 (C/C++)](../preprocessor/grammar-summary-c-cpp.md)
