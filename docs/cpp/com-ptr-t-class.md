---
title: _com_ptr_t 클래스
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t
helpviewer_keywords:
- _com_ptr_t class
ms.assetid: 3753a8a0-03d4-4cfd-8a9a-74872ea53971
ms.openlocfilehash: ce19dbc5f55460bb4bdbdee17f4fbbbcc8c6fd60
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154905"
---
# <a name="comptrt-class"></a>_com_ptr_t 클래스

**Microsoft 전용**

A **_com_ptr_t** 개체는 COM 인터페이스 포인터를 캡슐화 하 고 "스마트" 포인터 라고 합니다. 이 템플릿 클래스는 리소스 할당 및 할당 해제 함수 호출을 통해 관리 합니다 `IUnknown` 멤버 함수: `QueryInterface`, `AddRef`, 및 `Release`합니다.

스마트 포인터는 일반적으로 _COM_SMARTPTR_TYPEDEF 매크로 의해 제공 되는 typedef 정의에서 참조 됩니다. 이 매크로 인터페이스 이름과 IID 및의 특수화를 선언 **_com_ptr_t** 의 접미사로 인터페이스 이름의 `Ptr`합니다. 예를 들어:

```cpp
_COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));
```

선언 된 **_com_ptr_t** 특수화 `IMyInterfacePtr`합니다.

집합이 [템플릿 함수](../cpp/relational-function-templates.md),이 서식 파일의 멤버가 아닌 클래스 비교 연산자의 오른쪽에 있는 스마트 포인터를 사용 하 여 지원 비교 합니다.

### <a name="construction"></a>생성

|||
|-|-|
|[_com_ptr_t](../cpp/com-ptr-t-com-ptr-t.md)|생성 된 **_com_ptr_t** 개체입니다.|

### <a name="low-level-operations"></a>하위 수준 연산

|||
|-|-|
|[AddRef](../cpp/com-ptr-t-addref.md)|호출 된 `AddRef` 멤버 함수 `IUnknown` 캡슐화 된 인터페이스 포인터에 대 한 합니다.|
|[Attach](../cpp/com-ptr-t-attach.md)|이 스마트 포인터 형식의 원시 인터페이스 포인터를 캡슐화합니다.|
|[CreateInstance](../cpp/com-ptr-t-createinstance.md)|지정 된 개체의 새 인스턴스를 만듭니다는 `CLSID` 또는 `ProgID`합니다.|
|[Detach](../cpp/com-ptr-t-detach.md)|캡슐화된 인터페이스 포인터를 추출하고 반환합니다.|
|[GetActiveObject](../cpp/com-ptr-t-getactiveobject.md)|지정 된 개체의 기존 인스턴스에 연결 된 `CLSID` 또는 `ProgID`합니다.|
|[GetInterfacePtr](../cpp/com-ptr-t-getinterfaceptr.md)|캡슐화된 인터페이스 포인터가 반환됩니다.|
|[QueryInterface](../cpp/com-ptr-t-queryinterface.md)|호출 된 `QueryInterface` 멤버 함수 `IUnknown` 캡슐화 된 인터페이스 포인터에 대 한 합니다.|
|[릴리스](../cpp/com-ptr-t-release.md)|호출 된 `Release` 멤버 함수 `IUnknown` 캡슐화 된 인터페이스 포인터에 대 한 합니다.|

### <a name="operators"></a>연산자

|||
|-|-|
|[operator =](../cpp/com-ptr-t-operator-equal.md)|기존에 새 값을 할당 **_com_ptr_t** 개체입니다.|
|[operators ==, !=, \<, >, \<=, >=](../cpp/com-ptr-t-relational-operators.md)|스마트 포인터 개체를 다른 스마트 포인터, 원시 인터페이스 포인터를 비교 하거나 NULL.|
|[추출기](../cpp/com-ptr-t-extractors.md)|캡슐화된 COM 인터페이스 포인터를 추출합니다.|

**Microsoft 전용 종료**

## <a name="requirements"></a>요구 사항

**헤더:** \<comip.h >

**Lib:** comsuppw.lib 또는 comsuppwd.lib(자세한 내용은 [/zc: wchar_t(wchar_t는 네이티브 형식임)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)를 참조)

## <a name="see-also"></a>참고자료

[컴파일러 COM 지원 클래스](../cpp/compiler-com-support-classes.md)