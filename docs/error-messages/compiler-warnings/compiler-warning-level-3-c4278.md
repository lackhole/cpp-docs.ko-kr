---
title: 컴파일러 경고(수준 3) C4278
ms.date: 08/27/2018
f1_keywords:
- C4278
helpviewer_keywords:
- C4278
ms.assetid: 4b6053fb-df62-4c04-b6c8-c011759557b8
ms.openlocfilehash: 8c5c15105581602566116d3ed82b89a6337435c9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402166"
---
# <a name="compiler-warning-level-3-c4278"></a>컴파일러 경고(수준 3) C4278

> '*식별자*': 형식 라이브러리의 식별자 '*tlb*'가 이미 매크로 'rename' 한정자를 사용 하십시오.

사용 하는 경우 [#import](../../preprocessor/hash-import-directive-cpp.md)에 가져오는 typelib에 들어 있는 식별자는 식별자를 선언 하려고 *식별자*합니다. 그러나 이것이 이미 올바른 기호입니다.

사용 된 `#import` **이름 바꾸기** 기호 형식 라이브러리에 별칭을 지정 하는 특성입니다.