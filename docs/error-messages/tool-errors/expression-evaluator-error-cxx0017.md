---
title: 식 계산기 오류 CXX0017
ms.date: 11/04/2016
f1_keywords:
- CXX0017
helpviewer_keywords:
- CAN0017
- CXX0017
ms.assetid: af74db02-a64d-49ca-8363-3e044a107580
ms.openlocfilehash: bbf16ae9a503a8525edb42d6bf1fc4336c3f5267
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397135"
---
# <a name="expression-evaluator-error-cxx0017"></a>식 계산기 오류 CXX0017

기호를 찾을 수 없습니다

식에 지정 된 기호를 찾을 수 없습니다.

이 오류의 한 가지 가능한 원인은 기호 이름에 사례 일치 하지 않습니다. 때문에 C 및 C++ 은 대/소문자 구분의 언어는 대 소문자 구분 원본에 정의 된 기호 이름을 지정 해야 합니다.

이 오류는 디버깅 하는 동안 변수를 감시 하기 위해 변수 형식을 캐스팅 하려고 할 때 발생할 수 있습니다. `typedef` 형식에 대 한 새 이름을 선언 하지만 새 형식을 정의 하지 않습니다. 디버거에서 디버거에서 정의 된 형식 이름이 필요 합니다.

이 오류는 can0017과 동일 합니다.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>아래의 해결 방법 따라 수정합니다.

1. 기호 사용 되는 위치는 프로그램의 지점에 이미 선언 되어 있는지 확인 합니다.

1. 실제 형식 이름을 사용 하 여 변수를 캐스팅 하 여 디버거에서 아닌 `typedef`-이름을 정의 합니다.