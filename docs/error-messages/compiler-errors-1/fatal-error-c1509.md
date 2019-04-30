---
title: 심각한 오류 C1509
ms.date: 11/04/2016
f1_keywords:
- C1509
helpviewer_keywords:
- C1509
ms.assetid: 40dd100d-c6ba-451c-bd26-2c99ec1c36d6
ms.openlocfilehash: efd5b9dd5cdd7ee174bc786c38d9dd841e2ad6ce
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397486"
---
# <a name="fatal-error-c1509"></a>심각한 오류 C1509

컴파일러 한계: 'function' 함수에 예외 처리기 상태가 너무 많습니다. 함수를 간소화 합니다.

코드는 예외 처리기 상태가 (32,768 상태)는 내부 한계를 초과합니다.

가장 일반적인 원인은 함수 클래스 사용자 정의 변수 및 산술 연산자의 복잡 한 식을 포함 합니다.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>아래의 해결 방법 따라 수정합니다.

1. 일반적인 하위 식의 임시 변수를 할당 하 여 식을 간소화 합니다.

1. 함수를 좀 더 작은 함수로 분할 합니다.