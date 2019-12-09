---
title: 컴파일러 오류 C3839
ms.date: 11/04/2016
f1_keywords:
- C3839
helpviewer_keywords:
- C3839
ms.assetid: 0957faff-1e9f-439b-876b-85bd8d2c578d
ms.openlocfilehash: 19a1055a461d76856cc3bccbd9f8af0f0dcff356
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754929"
---
# <a name="compiler-error-c3839"></a>컴파일러 오류 C3839

관리되는 또는 WinRT 형식의 맞춤 방식을 변경할 수 없습니다.

관리 되는 형식 또는 Windows 런타임 형식의 변수 맞춤은 CLR 또는 Windows 런타임에 의해 제어 되며 [align](../../cpp/align-cpp.md)으로 수정할 수 없습니다.

다음 샘플에서는 C3839를 생성합니다.

```cpp
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
