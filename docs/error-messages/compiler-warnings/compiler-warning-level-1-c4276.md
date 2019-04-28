---
title: 컴파일러 경고(수준 1) C4276
ms.date: 11/04/2016
f1_keywords:
- C4276
helpviewer_keywords:
- C4276
ms.assetid: 9d738c2d-29e5-408a-b9ff-be1a850b2238
ms.openlocfilehash: 87f13f7da12a3f7e40aaad180e2a3bc83e121771
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207141"
---
# <a name="compiler-warning-level-1-c4276"></a>컴파일러 경고(수준 1) C4276

'function': 프로토타입을 입력 하지 않았습니다 매개 변수가 없는 것으로 간주

사용 하 여 함수의 주소를 수행 하는 시기를 [__stdcall](../../cpp/stdcall.md) 호출 규칙을 프로토타입을 제공 해야는 컴파일러가 함수의 데코레이팅된 이름을 만들 수 있도록 합니다. 이후 *함수* 컴파일러에 프로토타입이 없는 데코 레이트 된 이름을 만들 때에 함수에 매개 변수가 없는 것으로 가정 합니다.