---
title: 컴파일러 경고(수준 1) C4399
ms.date: 11/04/2016
f1_keywords:
- C4399
helpviewer_keywords:
- C4399
ms.assetid: f58d9ba7-71a0-4c3b-b26f-f946dda8af30
ms.openlocfilehash: 56fe0f314142d873fc02136bc2c3fe65e71f4dda
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408344"
---
# <a name="compiler-warning-level-1-c4399"></a>컴파일러 경고(수준 1) C4399

> '*기호*': /clr으로 컴파일될 때 __declspec (dllimport)을 사용 하 여 프로세스별 기호를 표시 하지 말아야 합니다: 순수

## <a name="remarks"></a>설명

**/clr: pure** 컴파일러 옵션은 Visual Studio 2015에서 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다.

순수 이미지에는 네이티브 이미지 또는 네이티브 및 CLR 구문을 사용 하 여 이미지에서 데이터를 가져올 수 있습니다. 이 경고를 해결 하려면 사용 하 여 컴파일합니다 **/clr** (하지 **/clr: pure**) 또는 삭제 `__declspec(dllimport)`합니다.

## <a name="example"></a>예제

다음 샘플 C4399를 생성합니다.

```cpp
// C4399.cpp
// compile with: /clr:pure /doc /W1 /c
__declspec(dllimport) __declspec(process) extern const int i;   // C4399
```