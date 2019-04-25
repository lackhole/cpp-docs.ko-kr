---
title: 컴파일러 오류 C2170
ms.date: 11/04/2016
f1_keywords:
- C2170
helpviewer_keywords:
- C2170
ms.assetid: d5c663f0-2459-4e11-a8bf-a52b62f3c71d
ms.openlocfilehash: 04d41a50bc0d5e811e47e5f9d146362a543f26f9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174681"
---
# <a name="compiler-error-c2170"></a>컴파일러 오류 C2170

'identifier': 함수로 선언 되지 내장 함수 일 수 없습니다

### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면

1. Pragma `intrinsic` 함수 이외의 항목에 사용 됩니다.

1. Pragma `intrinsic` 내장 형식이 없는 함수의 사용 됩니다.