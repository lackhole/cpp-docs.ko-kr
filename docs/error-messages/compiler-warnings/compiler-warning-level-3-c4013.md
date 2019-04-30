---
title: 컴파일러 경고 (수준 3) C4013
ms.date: 11/04/2016
f1_keywords:
- C4013
helpviewer_keywords:
- C4013
ms.assetid: 9f9afc71-6e78-463d-9d66-3012d6a3cd5d
ms.openlocfilehash: 2ec76fa5d83721137a5142d435f9c598527382f3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402400"
---
# <a name="compiler-warning-level-3-c4013"></a>컴파일러 경고 (수준 3) C4013

' function' 정의 되지 않았습니다. 가정 extern int를 반환 합니다.

컴파일러가 정의 되지 않은 함수에 대 한 호출을 발견 했습니다.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면

1. 함수 이름의 철자가 잘못 되었습니다

1. 외부 함수를 프로토타입화 되지 않았습니다. `extern`