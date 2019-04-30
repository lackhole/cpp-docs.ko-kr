---
title: 컴파일러 경고(수준 4) C4057
ms.date: 11/04/2016
f1_keywords:
- C4057
helpviewer_keywords:
- C4057
ms.assetid: e75d0645-84c9-4bef-a812-942ed9879aa3
ms.openlocfilehash: 234223ee7b6a031dd9e2c0fc88ccbbdba05beb3c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401438"
---
# <a name="compiler-warning-level-4-c4057"></a>컴파일러 경고(수준 4) C4057

'operator': 'identifier1'은 약간 다른 기본 형식에 대한 간접 참조가 'identifier2'와 다릅니다.

두 포인터 식은 다른 기본 형식을 참조합니다. 식을 변환하지 않고 사용합니다.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면

1. 부호 있는 형식과 부호 없는 형식을 혼합합니다.

1. **short** 및 **long** 형식을 혼합합니다.