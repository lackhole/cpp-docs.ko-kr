---
title: 컴파일러 오류 C3550
ms.date: 11/04/2016
f1_keywords:
- C3550
helpviewer_keywords:
- C3550
ms.assetid: 9f2d5ffc-e429-41a1-89e3-7acc4fd47e14
ms.openlocfilehash: 106ac93496eebb25ee603251d84680053e1310b7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375914"
---
# <a name="compiler-error-c3550"></a>컴파일러 오류 C3550

이 컨텍스트에 일반 'decltype(auto)'만 사용할 수 있습니다.

`decltype(auto)`을 함수 반환 형식의 자리 표시자로 사용하는 경우 자체에서 사용되어야 합니다. 포인터 선언(`decltype(auto*)`), 참조 선언(`decltype(auto&)`) 또는 이러한 기타 모든 한정의 일부로 사용할 수 없습니다.

## <a name="see-also"></a>참고자료

[auto](../../cpp/auto-cpp.md)