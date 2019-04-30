---
title: 명령줄 경고 D9043
ms.date: 11/04/2016
f1_keywords:
- D9043
helpviewer_keywords:
- D9043
ms.assetid: 9263e28d-217b-414c-bfb6-86efd3c27a77
ms.openlocfilehash: 62834c5f245bc1c0f6197638e4608b7fe71e7eb1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62213496"
---
# <a name="command-line-warning-d9043"></a>명령줄 경고 D9043

'compiler_option';에 대 한 ' warning_level' 값이 잘못 되었습니다 가정 '4999'; 코드 분석 경고가 경고 수준과 연결 되어 있지 않습니다.

## <a name="example"></a>예제

다음 샘플 C9043를 생성합니다.

```
// D9043.cpp
// compile with: /analyze /w16001
// D9043 warning expected
int main() {}
```