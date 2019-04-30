---
title: 첨자 연산자의 해석
ms.date: 08/27/2018
helpviewer_keywords:
- subscript operator [C++], interpretation of
- arrays [C++], subscripting
- interpreting subscript operators [C++]
- operators [C++], interpretation of subscript
ms.assetid: 8852ca18-9d5b-43f7-b8bd-abc89364fbf2
ms.openlocfilehash: 1c3d5bca66cb294503805fd5b7691331ac380ae5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375316"
---
# <a name="interpretation-of-subscript-operator"></a>첨자 연산자의 해석

다른 연산자와 달리 첨자 연산자(**\[ ]**)는 사용자가 다시 정의할 수 있습니다. 첨자 연산자의 기본 동작은 다음 메서드를 사용하여 배열 이름과 첨자를 결합하는 것입니다.

\*(( *array-name*) + ( *subscript*))

포인터 형식을 비롯한 모든 추가에서와 마찬가지로 해당 형식의 크기를 조정하기 위해 크기 조정이 자동으로 수행됩니다. 따라서 결과 값은 *array-name*의 원점부터 *subscript*바이트가 아니라 배열의 *subscript*번째 요소입니다. (이 변환에 대한 자세한 내용은 [덧셈 연산자](../cpp/additive-operators-plus-and.md)를 참조하세요.)

다차원 배열에서도 다음 메서드를 사용하여 주소가 파생됩니다.

((*array-name*) + (*subscript*1 \* *max*2 \* *max*3 \* ... \* *max*n) + (*subscript*2 \* *max*3 \* ... \* *max*n)... + + *subscript*n))

## <a name="see-also"></a>참고 항목

[배열(C++)](../cpp/arrays-cpp.md)<br/>
