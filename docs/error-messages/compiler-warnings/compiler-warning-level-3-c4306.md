---
title: 컴파일러 경고(수준 3) C4306
ms.date: 08/27/2018
f1_keywords:
- C4306
helpviewer_keywords:
- C4306
ms.assetid: 5b2192d7-402d-4b6d-8619-08105e7dcac7
ms.openlocfilehash: 78ec291b555838b1af63287e3d24fdb809afd7c4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402062"
---
# <a name="compiler-warning-level-3-c4306"></a>컴파일러 경고(수준 3) C4306

> '*식별자*': 변환할 '*type1*'to'*type2*' 큰 크기의

식별자가 형식 보다 큰 포인터에 캐스팅 합니다. 새 형식의 채워지지 않은 상위 비트가 0으로 채워진 됩니다.

이 경고는 의도 하지 않은 변환을 나타낼 수 있습니다. 결과 포인터는 유효 하지 않을 수 있습니다.