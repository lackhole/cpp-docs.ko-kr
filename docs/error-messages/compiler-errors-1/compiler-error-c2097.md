---
title: 컴파일러 오류 C2097
ms.date: 11/04/2016
f1_keywords:
- C2097
helpviewer_keywords:
- C2097
ms.assetid: 7e5b2fd4-f61c-4b8a-b265-93e987a04bd3
ms.openlocfilehash: 8b50221997dcf2fb60ee2b82ed630dd325a38145
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62377009"
---
# <a name="compiler-error-c2097"></a>컴파일러 오류 C2097

초기화가 잘못 되었습니다

### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면

1. 상수가 아닌 값으로 사용 하 여 변수를 초기화 합니다.

1. 긴 주소를 사용 하 여 짧은 주소를 초기화 합니다.

1. 로컬 구조체, 공용 구조체 또는 비상수 식 컴파일할 때 사용 하 여 배열 초기화 **/Za**합니다.

1. 쉼표 연산자를 포함 하는 식으로 초기화 합니다.

1. 이 아니고 기호화 된 상수는 식으로 초기화 합니다.