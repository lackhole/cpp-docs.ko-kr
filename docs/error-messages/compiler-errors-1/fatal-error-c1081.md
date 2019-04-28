---
title: 심각한 오류 C1081
ms.date: 11/04/2016
f1_keywords:
- C1081
helpviewer_keywords:
- C1081
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
ms.openlocfilehash: f3c9f9bde5da7fb120accbb9a8d72e5715ab9d2b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62229421"
---
# <a name="fatal-error-c1081"></a>심각한 오류 C1081

'symbol': 파일 이름이 너무 깁니다.

파일 경로 길이가 초과 `_MAX_PATH` (STDLIB.h에서 260 자 정의 됨). 파일의 이름을 줄이십시오.

짧은 파일 이름을 사용 하 여 CL.exe를 호출 하는 경우 컴파일러는 전체 경로 이름을 생성 해야 합니다. 예를 들어 `cl -c myfile.cpp` 생성 하도록 컴파일러에 발생할 수 있습니다.

```
D:\<very-long-directory-path>\myfile.cpp
```