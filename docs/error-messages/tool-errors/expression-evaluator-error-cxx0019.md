---
title: 식 계산기 오류 CXX0019
ms.date: 11/04/2016
f1_keywords:
- CXX0019
helpviewer_keywords:
- CXX0019
- CAN0019
ms.assetid: 4c6431fd-3310-4a61-934d-58b070b330fe
ms.openlocfilehash: 266e97f28cf0f27cb87e9743399c66aba87c0e8d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397109"
---
# <a name="expression-evaluator-error-cxx0019"></a>식 계산기 오류 CXX0019

잘못 된 형식 캐스팅

C 식 계산기 작성 하는 대로 형식 변환을 수행할 수 없습니다.

이 오류는 can0019와 동일 합니다.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면

1. 지정된 된 형식을 알려진 아닙니다.

1. 포인터 형식의 수준이 너무 많아 있었습니다. 예를 들어, 유형 변환

    ```
    (char **)h_message
    ```

   C 식 계산기에서 계산할 수 없습니다.