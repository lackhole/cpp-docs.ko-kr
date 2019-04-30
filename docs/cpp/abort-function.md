---
title: abort 함수
ms.date: 12/01/2017
helpviewer_keywords:
- abort function
ms.assetid: 3352bcc4-1a8a-4e1f-8dcc-fe30f6b50f2d
ms.openlocfilehash: 7c87cb4fe7349a0d623c765c20e7e213a8454571
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385104"
---
# <a name="abort-function"></a>abort 함수

표준 포함 파일 STDLIB.H에서 선언된 **abort** 함수는 C++ 프로그램을 종료합니다. `exit`와 **abort**의 차이는 `exit`에서는 C++ 런타임 종료 처리 과정이 발생하지만(전역 개체 소멸자 호출) **abort**에서는 프로그램이 즉시 종료된다는 점입니다. 자세한 내용은 *런타임 라이브러리에서* [abort](../c-runtime-library/reference/abort.md)를 참조하십시오.

## <a name="see-also"></a>참고 항목

[프로그램 종료](../cpp/program-termination.md)