---
title: 컴파일러 오류 C2708
ms.date: 11/04/2016
f1_keywords:
- C2708
helpviewer_keywords:
- C2708
ms.assetid: d52d3088-1141-42f4-829c-74755a7fcc3a
ms.openlocfilehash: a128613cabb201142c29b833959924dbf8a6e0ba
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160960"
---
# <a name="compiler-error-c2708"></a>컴파일러 오류 C2708

'identifier': 이전 호출 또는 참조와 다른 실제 매개 변수 길이 (바이트)

A [__stdcall](../../cpp/stdcall.md) 함수 프로토타입 뒤에 야 합니다. 이 고, 그렇지 컴파일러 해석 프로토타입으로 함수를 처음으로 호출 하 고 컴파일러와 일치 하지 않는 호출을 발견 하는 경우이 오류가 발생 합니다.

이 오류를 해결 하려면 함수 프로토타입을 추가 합니다.