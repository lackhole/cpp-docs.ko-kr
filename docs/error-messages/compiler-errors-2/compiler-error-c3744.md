---
title: 컴파일러 오류 C3744
ms.date: 11/04/2016
f1_keywords:
- C3744
helpviewer_keywords:
- C3744
ms.assetid: a447d050-80d1-406a-9a6e-f15c527d717c
ms.openlocfilehash: 407ed4b30b55b63aa9bf36de9f8675a531d70534
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62227113"
---
# <a name="compiler-error-c3744"></a>컴파일러 오류 C3744

__unhook 관리 되는 이벤트에 대 한 최소 3 개의 인수가 있어야 합니다.

합니다 [__unhook](../../cpp/unhook.md) 함수는 Managed Extensions for에 대 한 컴파일된 프로그램에서 사용 하는 경우 세 가지 매개 변수를 사용 해야 합니다 C++합니다.

`__hook` 및 `__unhook` /clr 프로그래밍을 사용 하 여 호환 되지 않습니다. 대신 + = 및-= 연산자를 사용 합니다.

C3744 사용 되지 않는 컴파일러 옵션을 사용 하 여 전용인 **/clr: oldsyntax**합니다.
