---
title: 식 계산기 오류 CXX0065
ms.date: 11/04/2016
f1_keywords:
- CXX0065
helpviewer_keywords:
- CAN0065
- CXX0065
ms.assetid: aac68f87-0b90-4c19-afa6-1c587625a5fd
ms.openlocfilehash: 7b62e42da2a74d910e2dc56ce2dfcb5cb38f2bfa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62299324"
---
# <a name="expression-evaluator-error-cxx0065"></a>식 계산기 오류 CXX0065

변수 스택 프레임이 필요합니다.

식은 현재 범위 내에 존재 하지만 아직 만들지 않은 변수를 포함 합니다.

아니면 함수에 대 한 종료 코드를 한 단계씩 함수 했지만 아직 함수에 대 한 스택 프레임 설정의 프롤로그를 실행 하는 경우이 오류가 발생할 수 있습니다.

식을 계산 하기 전에 스택 프레임 설정 된 하기까지 프롤로그 코드를 단계별로 실행 합니다.

이 오류는 can0065와 동일 합니다.