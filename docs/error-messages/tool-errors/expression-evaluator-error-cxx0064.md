---
title: 식 계산기 오류 CXX0064
ms.date: 11/04/2016
f1_keywords:
- CXX0064
helpviewer_keywords:
- CAN0064
- CXX0064
ms.assetid: aa509e71-0616-41ca-a94e-6c376b041e57
ms.openlocfilehash: 71e4e3e87b33849e6b487b79268ebc9574c2e5a6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62299480"
---
# <a name="expression-evaluator-error-cxx0064"></a>식 계산기 오류 CXX0064

바인딩된 가상 멤버 함수에 중단점을 설정할 수 없습니다.

와 같은 개체에 대 한 포인터를 통해 가상 멤버 함수에 중단점 설정 된:

```
pClass->vfunc( int );
```

와 같은 클래스를 입력 하 여 가상 함수에 중단점을 설정할 수 있습니다.

```
Class::vfunc( int );
```

이 오류는 can0064와 동일 합니다.