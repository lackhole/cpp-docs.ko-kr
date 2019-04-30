---
title: 리소스 컴파일러 심각한 오류 RW1025
ms.date: 11/04/2016
f1_keywords:
- RW1025
helpviewer_keywords:
- RW1025
ms.assetid: 561a02af-e7e0-442a-8ad3-a00b2ca1b62e
ms.openlocfilehash: 8ecfc11f5cc991294d966a4b6c75d8da6669d5b1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62347209"
---
# <a name="resource-compiler-fatal-error-rw1025"></a>리소스 컴파일러 심각한 오류 RW1025

먼 힙 메모리가 부족 합니다.

너무 많은 공간을 차지 하는 메모리 상주 소프트웨어를 확인 합니다. CHKDSK 프로그램을 사용 하 여 있는 메모리 양을 확인 합니다.

큰 리소스 파일을 만드는 경우 리소스 스크립트 두 파일로 분할 합니다. 두.res 파일을 만든 후 함께 연결 하는 MS-DOS 명령줄을 사용 합니다.

```
copy first.res /b + second.res /b full.res
```