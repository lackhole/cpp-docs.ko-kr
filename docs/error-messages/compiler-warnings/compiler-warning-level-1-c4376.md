---
title: 컴파일러 경고(수준 1) C4376
ms.date: 11/04/2016
f1_keywords:
- C4376
helpviewer_keywords:
- C4376
ms.assetid: 5f202c74-9489-48fe-b36f-19cd882b1589
ms.openlocfilehash: b1f6e7b403931f7fe1a67974ae85001cf80eab66
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410436"
---
# <a name="compiler-warning-level-1-c4376"></a>컴파일러 경고(수준 1) C4376

액세스 지정자 ' old_specifier:'는 지원 되지 않습니다: 사용 하십시오 ' new_specifier:' 대신

메타 데이터의 형식 및 멤버 접근성을 지정 하는 방법은 참조 하세요. [표시 유형 입력](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) 하 고 [멤버 표시 유형](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility) 에서 [방법: 클래스 및 구조체 정의 및 사용 (C++/CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)합니다.

## <a name="example"></a>예제

다음 샘플 C4376를 생성합니다.

```
// C4376.cpp
// compile with: /clr /W1 /c
public ref class G {
public public:   // C4376
   void m2();
};

public ref class H {
public:   // OK
   void m2();
};
```