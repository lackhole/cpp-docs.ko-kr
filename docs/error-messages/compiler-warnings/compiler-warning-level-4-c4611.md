---
title: 컴파일러 경고(수준 4) C4611
ms.date: 11/04/2016
f1_keywords:
- C4611
helpviewer_keywords:
- C4611
ms.assetid: bd90d0a6-75f9-4e97-968d-dda6773e9fd8
ms.openlocfilehash: b799c568d73a081a4d4cf5616f376f3efc9eeffb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349674"
---
# <a name="compiler-warning-level-4-c4611"></a>컴파일러 경고(수준 4) C4611

'function' 간의 상호 작용 하 고 C++ 개체 소멸 이식 가능 하지 않습니다

일부 플랫폼에서는 포함 하는 함수 **catch** 지원 되지 않을 수 있습니다 C++ 범위를 벗어날 때 소멸의 의미 체계 개체입니다.

예기치 않은 동작을 방지 하려면 사용 하지 않도록 **catch** 생성자와 소멸자가 있는 함수에 있습니다.

이 경고는 한 번만 발생 참조 [pragma 경고](../../preprocessor/warning.md)합니다.