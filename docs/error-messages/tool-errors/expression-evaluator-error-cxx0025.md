---
title: 식 계산기 오류 CXX0025
ms.date: 11/04/2016
f1_keywords:
- CXX0025
helpviewer_keywords:
- CAN0025
- CXX0025
ms.assetid: 3e2fb541-63b3-46ac-9f93-3dadb253bcf6
ms.openlocfilehash: 695a6e909717fe38dd8db6f4981db0d756fbb390
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62359829"
---
# <a name="expression-evaluator-error-cxx0025"></a>식 계산기 오류 CXX0025

연산자에는 구조체/공용 구조체가 필요합니다.

식을 사용 하는 연산자 `struct` 또는 **union** 형식이 없는 식을 적용할를 `struct` 또는 **union**합니다.

클래스, 구조체 또는 공용 구조체 변수의 구성 요소는 정규화 된 이름이 있어야 합니다. 전체 사양이 없는 구성 요소를 입력할 수 없습니다.

이 오류는 can0025와 동일 합니다.