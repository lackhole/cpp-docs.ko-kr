---
title: 특성 프로그래밍 FAQ
ms.date: 10/02/2018
ms.topic: conceptual
helpviewer_keywords:
- attributed programming
- attributes [C++/CLI], frequently asked questions
- FAQs (frequently asked questions), attributed programming [C++]
ms.assetid: a1b8349f-7f51-43c4-95ea-4edb6e5f243f
ms.openlocfilehash: fd4c24e3933738d128dffd41018466c33b419de8
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59025100"
---
# <a name="attribute-programming-faq"></a>특성 프로그래밍 FAQ

이 항목에서는 다음 자주 묻는 질문에 대답 합니다.

- [HRESULT는 무엇입니까?](#vcconattributeprogrammmingfaqanchor1)

- [특성에 대 한 매개 변수 이름을 지정 해야 하는 경우는 합니까?](#vcconattributeprogrammmingfaqanchor2)

- [주석 특성 블록에서 사용할 수 있나요?](#vcconattributeprogrammmingfaqanchor3)

- [상속을 사용 하 여 특성 작용 수행 하는 방법](#vcconattributeprogrammmingfaqanchor4)

- [하지 않는 ATL 프로젝트의 특성을 사용 하는 방법](#vcconattributeprogrammmingfaqanchor5)

- [특성 사용된 프로젝트에.idl 파일을 사용 하는 방법](#vcconattributeprogrammmingfaqanchor6)

- [특성에 의해 삽입 된 코드를 수정할 수 있나요?](#vcconattributeprogrammmingfaqanchor7)

- [앞으로 특성 가진된 인터페이스를 선언할 수는 방법](#vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface)

- [또한 특성을 사용 하는 클래스에서 파생 된 클래스에 특성을 사용할 수 있나요?](#vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor)

##  <a name="vcconattributeprogrammmingfaqanchor1"></a> HRESULT는 무엇입니까?

HRESULT는 자주 사용 되는 반환 값으로 특성 및 ATL 일반적 단순 데이터 형식입니다. 다음 표에서 다양 한 값을 보여 줍니다. 더 많은 값은 헤더 파일은 winerror.h에 포함 됩니다.

|이름|설명|값|
|----------|-----------------|-----------|
|S_OK|작업 성공|0x00000000|
|E_UNEXPECTED|예기치 않은 오류|0x8000FFFF|
|E_NOTIMPL|구현 되지 않음|0x80004001|
|E_OUTOFMEMORY|필요한 메모리를 할당 하지 못했습니다.|0x8007000E|
|E_INVALIDARG|하나 이상의 인수가 올바르지 않습니다.|0x80070057|
|E_NOINTERFACE|인터페이스|0x80004002|
|E_POINTER|잘못 된 포인터|0x80004003|
|E_HANDLE|잘못 된 핸들|0x80070006|
|E_ABORT|작업이 중단 되었습니다|0x80004004|
|E_FAIL|지정 되지 않은 오류|0x80004005|
|E_ACCESSDENIED|일반 액세스 거부 오류|0x80070005|

##  <a name="vcconattributeprogrammmingfaqanchor2"></a> 특성에 대 한 매개 변수 이름을 지정 해야 하는 경우는 합니까?

대부분의 경우에서 특성에는 단일 매개 변수가 해당 매개 변수 명명 됩니다. 이 이름은 코드에 특성을 삽입 하는 경우 필요 하지 않습니다. 예를 들어, 다음 사용 합니다 [집계할](aggregatable.md) 특성:

```cpp
[coclass, aggregatable(value=allowed)]
class CMyClass
{
// The class declaration
};
```

정확히와 같습니다.

```cpp
[coclass, aggregatable(allowed)]
class CMyClass
{
// The class declaration
};
```

그러나 다음과 같은 특성에 단일, 명명 되지 않은 매개 변수

||||
|-|-|-|
|[call_as](call-as.md)|[case](case-cpp.md)|[cpp_quote](cpp-quote.md)|
|[default](default-cpp.md)|[defaultvalue](defaultvalue.md)|[defaultvtable](defaultvtable.md)|
|[emitidl](emitidl.md)|[entry](entry.md)|[first_is](first-is.md)|
|[helpcontext](helpcontext.md)|[helpfile](helpfile.md)|[helpstring](helpstring.md)|
|[helpstringcontext](helpstringcontext.md)|[typelib](helpstringdll.md)|[ID](id.md)|
|[iid_is](iid-is.md)|[import](import.md)|[importlib](importlib.md)|
|[include](include-cpp.md)|[includelib](includelib-cpp.md)|[last_is](last-is.md)|
|[length_is](length-is.md)|[max_is](max-is.md)|[no_injected_text](no-injected-text.md)|
|[pointer_default](pointer-default.md)|[pragma](pragma.md)|[restricted](restricted.md)|
|[size_is](size-is.md)|[원본](source-cpp.md)|[switch_is](switch-is.md)|
|[switch_type](switch-type.md)|[transmit_as](transmit-as.md)|[wire_marshal](wire-marshal.md)|

##  <a name="vcconattributeprogrammmingfaqanchor3"></a> 주석 특성 블록에서 사용할 수 있나요?

특성 블록 내에서 한 줄 및 여러 줄 주석을 사용할 수 있습니다. 그러나 주석 특성은 매개 변수가 들어 있는 괄호 안에 두 스타일 중 하나를 사용할 수 없습니다.

다음은 허용 됩니다.

```cpp
[ coclass, progid("MyClass.CMyClass.1"), /* Multiple-line
                                       comment */
   threading("both") // Single-line comment
]
```

다음은 허용 되지 않습니다.

```cpp
[ coclass, progid("MyClass.CMyClass.1" /* Multiple-line comment */ ), threading("both" // Single-line comment)
]
```

##  <a name="vcconattributeprogrammmingfaqanchor4"></a> 상속을 사용 하 여 특성 작용 수행 하는 방법

특성을 사용 하 고 해결 되지 않은 클래스 있습니다 자체 때문일 여부는 다른 클래스에서 상속할 수 있습니다. 특성 사용된 하는 클래스에서 파생 하는 결과 특성 공급자가 해당 코드를 변환 된 후 해당 클래스에서 파생와 같습니다. 특성은 파생 클래스 c + + 상속을 통해 전송 되지 않습니다. 특성 공급자만 해당 특성 유사 하 게 코드를 변환합니다.

##  <a name="vcconattributeprogrammmingfaqanchor5"></a> 하지 않는 ATL 프로젝트의 특성을 사용 하는 방법

.Idl 파일에는 하지 않는 ATL 프로젝트를 해야 하 고 특성 사용된 개체 추가 시작 하는 것이 좋습니다. 이 경우에 사용 된 **클래스 추가 마법사** 코드를 제공 합니다.

##  <a name="vcconattributeprogrammmingfaqanchor6"></a> 특성 사용된 프로젝트에.idl 파일을 사용 하는 방법

특성 사용 ATL 프로젝트에서 사용 하려는.idl 파일이 있을 수 있습니다. 사용이 경우에 [importidl](importidl.md) 특성,.h 파일.idl 파일을 컴파일할 (참조는 [MIDL Property Pages](../../build/reference/midl-property-pages.md) 프로젝트의 **속성 페이지** 대화 상자), 및 그런 다음 프로젝트에.h 파일을 포함 합니다.

##  <a name="vcconattributeprogrammmingfaqanchor7"></a> 특성에 의해 삽입 된 코드를 수정할 수 있나요?

일부 특성 프로젝트에 코드를 삽입합니다. 사용 하 여 삽입된 된 코드를 볼 수는 [/Fx](../../build/reference/fx-merge-injected-code.md) 컴파일러 옵션입니다. 삽입된 된 파일에서 코드를 복사 하 고 소스 코드에 붙여 넣습니다 수 이기도 합니다. 이 특성의 동작을 수정할 수 있습니다. 그러나 다른 부분 에서도 코드를 수정 해야 합니다.

다음 샘플은 소스 코드 파일에 삽입 된 코드를 복사 하는 결과.

```cpp
// attr_injected.cpp
// compile with: comsupp.lib
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>

[ module(name="MyLibrary") ];

// ITestTest
[
   object, uuid("DADECE00-0FD2-46F1-BFD3-6A0579CA1BC4"), dual, helpstring("ITestTest Interface"), pointer_default(unique)
]

__interface ITestTest : IDispatch {
   [id(1), helpstring("method DoTest")]
   HRESULT DoTest([in] BSTR str);
};

// _ITestTestEvents
[
   uuid("12753B9F-DEF4-49b0-9D52-A79C371F2909"), dispinterface, helpstring("_ITestTestEvents Interface")
]

__interface _ITestTestEvents {
   [id(1), helpstring("method BeforeChange")] HRESULT BeforeChange([in] BSTR str, [in,out] VARIANT_BOOL* bCancel);
};

// CTestTest
[
   coclass, threading(apartment), vi_progid("TestATL1.TestTest"), progid("TestATL1.TestTest.1"), version(1.0), uuid("D9632007-14FA-4679-9E1C-28C9A949E784"), // this line would be commented out from original file
   // event_source("com"), // this line would be added to support injected code
   source(_ITestTestEvents), helpstring("TestTest Class")
]

class ATL_NO_VTABLE CTestTest : public ITestTest,
// the following base classes support added injected code
public IConnectionPointContainerImpl<CTestTest>,
public IConnectionPointImpl<CTestTest, &__uuidof(::_ITestTestEvents), CComDynamicUnkArray>
{
public:
   CTestTest() {
   }
   // this line would be commented out from original file
   // __event __interface _ITestTestEvents;
   DECLARE_PROTECT_FINAL_CONSTRUCT()
   HRESULT FinalConstruct() {
      return S_OK;
   }

void FinalRelease() {}

public:
   CComBSTR m_value;
   STDMETHOD(DoTest)(BSTR str) {
      VARIANT_BOOL bCancel = FALSE;
      BeforeChange(str,&bCancel);
      if (bCancel) {
          return Error("Error : Someone don't want us to change the value");
      }

   m_value =str;
   return S_OK;
    }
// the following was copied in from the injected code.
HRESULT BeforeChange(::BSTR i1,::VARIANT_BOOL* i2) {
   HRESULT hr = S_OK;
   IConnectionPointImpl<CTestTest, &__uuidof(_ITestTestEvents), CComDynamicUnkArray>* p = this;
   VARIANT rgvars[2];
   Lock();
   IUnknown** pp = p->m_vec.begin();
   Unlock();
   while (pp < p->m_vec.end()) {
      if (*pp != NULL) {
         IDispatch* pDispatch = (IDispatch*) *pp;
         ::VariantInit(&rgvars[1]);
         rgvars[1].vt = VT_BSTR;
         V_BSTR(&rgvars[1])= (BSTR) i1;
         ::VariantInit(&rgvars[0]);
         rgvars[0].vt = (VT_BOOL | VT_BYREF);
         V_BOOLREF(&rgvars[0])= (VARIANT_BOOL*) i2;
         DISPPARAMS disp = { rgvars, NULL, 2, 0 };
         VARIANT ret_val;
         hr = __ComInvokeEventHandler(pDispatch, 1, 1, &disp, &ret_val);
         if (FAILED(hr))
            break;
      }
      pp++;
   }
   return hr;
}

BEGIN_CONNECTION_POINT_MAP(CTestTest)
CONNECTION_POINT_ENTRY(__uuidof(::_ITestTestEvents))
END_CONNECTION_POINT_MAP()
// end added code section

// _ITestCtrlEvents Methods
public:
};

int main() {}
```

##  <a name="vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface"></a> 앞으로 특성 가진된 인터페이스를 선언할 수는 방법

특성 가진된 인터페이스의 정방향 선언 되도록 하려는 경우에 실제 인터페이스 선언에 적용 되는 정방향 선언에 동일한 특성을 적용 해야 합니다. 적용 해야 합니다 [내보내기](export.md) 정방향 선언 하는 특성입니다.

##  <a name="vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor"></a> 또한 특성을 사용 하는 클래스에서 파생 된 클래스에 특성을 사용할 수 있나요?

아니요, 또한 특성을 사용 하는 클래스에서 파생 된 클래스에서 특성을 사용 하 여도 지원 되지 않습니다.

## <a name="see-also"></a>참고자료

[COM 및.NET에 대한 C++ 특성](cpp-attributes-com-net.md)