---
title: 식 계산기 오류 CXX0030
ms.date: 11/04/2016
f1_keywords:
- CXX0030
helpviewer_keywords:
- CAN0030
- CXX0030
ms.assetid: ada8b48c-09c8-49bf-ae23-313ed663c4fe
ms.openlocfilehash: 1e52b238905fba5c310a89377b81548a1c6b5784
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62359802"
---
# <a name="expression-evaluator-error-cxx0030"></a>식 계산기 오류 CXX0030

식을 계산할 수 없습니다.

기록의 디버거 식 계산기는 식에 대 한 값을 얻지 못했습니다. 가능한 원인 중 하나는 식이 프로그램의 주소 공간 밖에 있는 메모리 참조 (한 가지 예는 null 포인터 역참조). Windows는 프로그램의 주소 공간 밖에 있는 메모리에 대 한 액세스를 허용 하지 않습니다.

식 평가 순서를 제어 하려면 괄호를 사용 하 여 다시 작성할 수도 있습니다.

이 오류는 can0030과 동일 합니다.