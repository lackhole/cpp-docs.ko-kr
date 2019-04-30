---
title: 컴파일러 오류 C3839
ms.date: 11/04/2016
f1_keywords:
- C3839
helpviewer_keywords:
- C3839
ms.assetid: 0957faff-1e9f-439b-876b-85bd8d2c578d
ms.openlocfilehash: b8382213fbe7cc953dafd9610bfb993ba7837947
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400073"
---
# <a name="compiler-error-c3839"></a>컴파일러 오류 C3839

관리되는 또는 WinRT 형식의 맞춤 방식을 변경할 수 없습니다.

변수의 맞춤 관리 또는 Windows 런타임 형식 CLR 또는 Windows 런타임에서 제어 되며 수정할 수 없습니다 [맞춤](../../cpp/align-cpp.md)합니다.

다음 샘플에서는 C3839를 생성합니다.

```
// C3839a.cpp
// compile with: /clr
ref class C
{
public:
   __declspec(align(32)) int m_j; // C3839
};

int main()
{
}
```