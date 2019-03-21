---
title: Serialization(C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- serialization [C++]
- SerializableAttribute class, managed applications
- NonSerializedAttribute class, managed applications
- managed code [C++], serializing
- .NET Framework [C++], serialization
- serialization [C++], about serialization
ms.assetid: 869010ca-74e1-4989-b409-4643cdb94084
ms.openlocfilehash: 794a71ae9a146b691ba6a4377a7fdf2c3ddd3501
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57741395"
---
# <a name="serialization-ccli"></a>Serialization(C++/CLI)

Serialization (개체 또는 멤버를 영구적인 매체의 상태를 저장 하는 프로세스) (개별 필드 또는 속성 포함)는 관리 되는 클래스에서 지원 되는 <xref:System.SerializableAttribute> 및 <xref:System.NonSerializedAttribute> 클래스입니다.

## <a name="remarks"></a>설명

적용 된 **SerializableAttribute** 전체 클래스를 serialize 하거나에 특정 필드 또는 관리 되는 클래스의 부분을 직렬화 할 속성을 적용할 관리 되는 클래스 사용자 지정 특성입니다. 사용 된 **NonSerializedAttribute** 제외 필드 또는 관리 되는 클래스의 속성에서 serialize 되 고 사용자 지정 특성입니다.

## <a name="example"></a>예제

### <a name="description"></a>설명

다음 예제에서는 클래스에에서 `MyClass` (속성과 `m_nCount`) 직렬화 가능으로 표시 됩니다. 그러나 합니다 `m_nData` 나타난 것 처럼 속성이 serialize 되지 않습니다 합니다 **NonSerialized** 사용자 지정 특성:

### <a name="code"></a>코드

```
// serialization_and_mcpp.cpp
// compile with: /LD /clr
using namespace System;

[ Serializable ]
public ref class MyClass {
public:
   int m_nCount;
private:
   [ NonSerialized ]
   int m_nData;
};
```

### <a name="comments"></a>설명

두 특성 모두 해당 "짧은 이름"을 사용 하 여 참조할 수 있는지 확인 (**Serializable** 하 고 **NonSerialized**). 이에 설명 된 [Applying Attributes](/dotnet/standard/attributes/applying-attributes)합니다.

## <a name="see-also"></a>참고자료

[C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
