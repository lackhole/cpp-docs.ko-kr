---
title: 심각한 오류 C1054
ms.date: 11/04/2016
f1_keywords:
- C1054
helpviewer_keywords:
- C1054
ms.assetid: 9cfb7307-b22a-4418-b7c0-2621b0ab5b1b
ms.openlocfilehash: 0bfd0c03378b1a9c616a014ac96153b3ab04af9d
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344793"
---
# <a name="fatal-error-c1054"></a>심각한 오류 C1054

컴파일러 한계: 이니셜라이저가 너무 많이 중첩

이니셜라이저 (초기화 되는 형식의 조합에 따라 10 ~ 15 개 수준)에 중첩 한계를 초과 하는 코드입니다.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>아래의 해결 방법 따라 수정합니다.

1. 중첩을 줄이기 위해 초기화 되는 데이터 형식을 간소화 합니다.

1. 선언 후 별도 문에서 변수를 초기화 합니다.