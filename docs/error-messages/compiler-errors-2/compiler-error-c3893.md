---
title: 컴파일러 오류 C3893
ms.date: 11/04/2016
f1_keywords:
- C3893
helpviewer_keywords:
- C3893
ms.assetid: 90d52eae-6ef2-4db1-b7ad-92f9e8b140fb
ms.openlocfilehash: 45a140d3fd5f510ee2434950ca3c4b47c0756d75
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385500"
---
# <a name="compiler-error-c3893"></a>컴파일러 오류 C3893

'var': initonly 데이터 멤버의 값 (l-value)-사용 'type_name' 클래스의 인스턴스 생성자 에서만 허용 됩니다

정적 [initonly](../../dotnet/initonly-cpp-cli.md) 데이터 멤버는 정적 생성자의 주소를 하나만 사용할 수 있습니다.

인스턴스 (비정적) initonly 데이터 멤버 인스턴스 (비정적) 생성자의 주소를 하나만 사용할 수 있습니다.

다음 샘플에서는 C3893를 생성합니다.

```
// C3893.cpp
// compile with: /clr
ref struct Y1 {
   Y1() : data_var(0) {
      int% i = data_var;   // OK
   }
   initonly int data_var;
};

int main(){
   Y1^ y= gcnew Y1;
   int% i = y->data_var;   // C3893
}
```