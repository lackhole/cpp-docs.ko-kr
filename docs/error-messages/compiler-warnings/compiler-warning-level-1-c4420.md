---
title: 컴파일러 경고(수준 1) C4420
ms.date: 11/04/2016
f1_keywords:
- C4420
helpviewer_keywords:
- C4420
ms.assetid: 44a37754-7ddd-4764-a5f7-d33e05c20091
ms.openlocfilehash: a4a7e91e7845cc0fc25d5a6fad16ae7b7e327952
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408175"
---
# <a name="compiler-warning-level-1-c4420"></a>컴파일러 경고(수준 1) C4420

'operator': '연산자'를 대신 사용 하 여 연산자를 사용할 수 없는 런타임 검사가 손상 될 수 있습니다.

사용 하는 경우이 경고는 발생 합니다 [/RTCv](../../build/reference/rtc-run-time-error-checks.md) (새로운/삭제 확인 vector) 벡터 형식이 없으므로 검색 되 면 및 합니다. 이 경우 비 벡터 형식은 사용 됩니다.

/Rtcv가 제대로 작동 하려면에서 컴파일러는 항상 호출 해야 벡터 형식의 [새](../../cpp/new-operator-cpp.md)/[삭제](../../cpp/delete-operator-cpp.md) 벡터 구문이 사용 된 경우.