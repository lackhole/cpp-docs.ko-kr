---
title: com::ptr 클래스
ms.date: 01/16/2019
ms.topic: reference
f1_keywords:
- msclr::com::ptr::ptr
- msclr::com::ptr::Attach
- msclr::com::ptr::CreateInstance
- msclr::com::ptr::Detach
- msclr::com::ptr::GetInterface
- msclr::com::ptr::QueryInterface
- msclr::com::ptr::Release
- msclr::com::ptr::operator=
- msclr::com::ptr::operator->
- msclr::com::ptr::operator!
helpviewer_keywords:
- msclr::ptr class
ms.assetid: 0144d0e4-919c-45f9-a3f8-fbc9edba32bf
ms.openlocfilehash: 342c222b837e179e2e13dbbd27c88efc18b12332
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58774173"
---
# <a name="comptr-class"></a>com::ptr 클래스

CLR 클래스의 멤버로 사용할 수 있는 COM 개체에 대한 래퍼입니다.  이 래퍼는 또한 COM 개체의 수명 주기 관리를 자동화하여 소멸자가 호출될 때 개체에서 모든 소유 참조를 해제합니다. 비슷합니다 [CComPtr 클래스](../atl/reference/ccomptr-class.md)합니다.

## <a name="syntax"></a>구문

```
template<class _interface_type>
ref class ptr;
```

### <a name="parameters"></a>매개 변수

*_interface_type*<br/>
COM 인터페이스.

## <a name="remarks"></a>설명

또한 `com::ptr`은 로컬 함수 변수로 사용하여 여러 COM 작업을 간소화하고 수명 주기 관리를 자동화할 수 있습니다.

A `com::ptr` 함수 매개 변수로 직접 사용할 수 없습니다; 사용을 [추적 참조 연산자](../extensions/tracking-reference-operator-cpp-component-extensions.md) 또는 [개체 연산자 (^)에 대 한 핸들](../extensions/handle-to-object-operator-hat-cpp-component-extensions.md) 대신 합니다.

`com::ptr` 함수에서 직접 반환 될 수 없습니다; 대신 핸들을 사용 합니다.

## <a name="example"></a>예제

이 예제에서는 `com::ptr`을 사용해서 해당 개인 멤버 `IXMLDOMDocument` 개체를 래핑하는 CLR 클래스를 구현합니다.  클래스의 공용 메서드를 호출하면 포함된 `IXMLDOMDocument` 개체가 호출됩니다.  이 샘플은 XML 문서의 인스턴스를 만들고, 여기에 일부 간단한 XML을 채우고, 구문 분석된 문서 트리에서 간소화된 노드 작업을 수행하고 XML을 콘솔에 출력합니다.

```cpp
// comptr.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   void LoadXml(String^ xml) {
      pin_ptr<const wchar_t> pinnedXml = PtrToStringChars(xml);
      BSTR bstr = NULL;

      try {
         // load some XML into the document
         bstr = ::SysAllocString(pinnedXml);
         if (NULL == bstr) {
            throw gcnew OutOfMemoryException;
         }
         VARIANT_BOOL bIsSuccessful = false;
         // use operator -> to call IXMODOMDocument member function
         Marshal::ThrowExceptionForHR(m_ptrDoc->loadXML(bstr, &bIsSuccessful));
      }
      finally {
         ::SysFreeString(bstr);
      }
   }

   // simplified function to write just the first xml node to the console
   void WriteXml() {
      IXMLDOMNode* pNode = NULL;

      try {
         // the first child of the document is the first real xml node
         Marshal::ThrowExceptionForHR(m_ptrDoc->get_firstChild(&pNode));
         if (NULL != pNode) {
            WriteNode(pNode);
         }
      }
      finally {
         if (NULL != pNode) {
            pNode->Release();
         }
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   // simplified function that only writes the node
   void WriteNode(IXMLDOMNode* pNode) {
      BSTR bstr = NULL;

      try {
         // write out the name and text properties
         Marshal::ThrowExceptionForHR(pNode->get_nodeName(&bstr));
         String^ strName = gcnew String(bstr);
         Console::Write("<{0}>", strName);
         ::SysFreeString(bstr);
         bstr = NULL;

         Marshal::ThrowExceptionForHR(pNode->get_text(&bstr));
         Console::Write(gcnew String(bstr));
         ::SysFreeString(bstr);
         bstr = NULL;

         Console::WriteLine("</{0}>", strName);
      }
      finally {
         ::SysFreeString(bstr);
      }
   }

   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // stream some xml into the document
      doc.LoadXml("<word>persnickety</word>");

      // write the document to the console
      doc.WriteXml();
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
}
```

```Output
<word>persnickety</word>
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명| 
|---------|-----------| 
|[ptr::ptr](#ptr)|생성 된 `com::ptr` COM 개체를 래핑할 합니다.| 
|[ptr::~ptr](#tilde-ptr)|소멸을 `com::ptr`입니다.| 

### <a name="public-methods"></a>public 메서드

|이름|설명|
|---------|-----------| 
|[ptr::Attach](#attach)|COM 개체를 연결 된 `com::ptr`합니다.| 
|[ptr::CreateInstance](#createInstance)|내에서 COM 개체의 인스턴스를 만듭니다를 `com::ptr`입니다.| 
|[ptr::Detach](#detach)|개체에 대 한 포인터를 반환 하는 COM 개체의 소유권을 포기 합니다.| 
|[ptr::GetInterface](#getInterface)|내에서 COM 개체의 인스턴스를 만듭니다를 `com::ptr`입니다.| 
|[ptr::QueryInterface](#queryInterface)|인터페이스에 대 한 소유 COM 개체를 쿼리하고 결과를 다른 연결 `com::ptr`합니다.| 
|[ptr::Release](#release)|COM 개체에 대 한 모든 소유 참조를 해제합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|---------|-----------| 
|[ptr::operator-&gt;](#operator-arrow)|멤버 액세스 연산자를 소유 하는 COM 개체에서 메서드를 호출 하는 데 사용 합니다.| 
|[ptr::operator=](#operator-assign)|COM 개체를 연결 된 `com::ptr`합니다.| 
|[ptr::operator&nbsp;bool](#operator-bool)|연산자를 사용 하 여 `com::ptr` 조건식에서입니다.| 
|[ptr::operator!](#operator-logical-not)|소유 하는 COM 개체 잘못 인지 확인 하는 연산자입니다.| 

## <a name="requirements"></a>요구 사항

**헤더 파일** \<msclr\com\ptr.h >

**Namespace** msclr:: com

 

## <a name="ptr"></a>ptr::ptr

소유 COM 개체에 대 한 포인터를 반환합니다.

```cpp
ptr();
ptr(
   _interface_type * p
);
```

### <a name="parameters"></a>매개 변수

*P*<br/>
COM 인터페이스 포인터.

### <a name="remarks"></a>설명

인수 없는 생성자 할당 `nullptr` 기본 개체 핸들입니다. 미래에 대 한 호출을 `com::ptr` 내부 개체의 유효성을 검사 하며 자동으로 개체를 만들거나 연결 될 때까지 실패 합니다.

단일 인수 생성자는 COM 개체에 대 한 참조를 추가 하지만 호출자에 게 호출 해야 하므로 호출자의 참조를 배출 하지 않는 `Release` 에서 COM 개체를 완전히 제어를 포기 합니다. 경우는 `com::ptr`의 소멸자가 호출 COM 개체의 참조를 자동으로 해제 됩니다.

전달 `NULL` 이 생성자에 인수가 없는 버전을 호출 하는 것과 같습니다.

### <a name="example"></a>예제

이 예제에서는 `com::ptr`을 사용해서 해당 개인 멤버 `IXMLDOMDocument` 개체를 래핑하는 CLR 클래스를 구현합니다. 생성자의 두 버전의 사용을 보여 줍니다.

```cpp
// comptr_ptr.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // construct the internal com::ptr with a COM object
   XmlDocument(IXMLDOMDocument* pDoc) : m_ptrDoc(pDoc) {}

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create an XML DOM document object
      Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
         CLSCTX_ALL, IID_IXMLDOMDocument, (void**)&pDoc));
      // construct the ref class with the COM object
      XmlDocument doc1(pDoc);

      // or create the class from a progid string
      XmlDocument doc2("Msxml2.DOMDocument.3.0");
   }
   // doc1 and doc2 destructors are called when they go out of scope
   // and the internal com::ptr releases its reference to the COM object
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="tilde-ptr"></a>ptr::~ptr

소멸을 `com::ptr`입니다.

```cpp
~ptr();
```

### <a name="remarks"></a>설명

소멸 된 `com::ptr` 해당 COM 개체를 소유 하는 모든 참조를 해제 합니다. COM 개체를 보유 하는 다른 참조를 가정 COM 개체가 삭제 되 고 해당 메모리를 해제 합니다.

### <a name="example"></a>예제

이 예제에서는 `com::ptr`을 사용해서 해당 개인 멤버 `IXMLDOMDocument` 개체를 래핑하는 CLR 클래스를 구현합니다.  에 `main` 함수, 두 개의 `XmlDocument` 개체 소멸자의 범위를 벗어날 때 호출 되는 `try` 블록 내부에서 결과 `com::ptr` 소멸자가 호출 되 COM에 대 한 모든 소유 참조를 해제 개체입니다.

```cpp
// comptr_dtor.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // construct the internal com::ptr with a COM object
   XmlDocument(IXMLDOMDocument* pDoc) : m_ptrDoc(pDoc) {}

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create an XML DOM document object
      Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
         CLSCTX_ALL, IID_IXMLDOMDocument, (void**)&pDoc));
      // construct the ref class with the COM object
      XmlDocument doc1(pDoc);

      // or create the class from a progid string
      XmlDocument doc2("Msxml2.DOMDocument.3.0");
   }
   // doc1 and doc2 destructors are called when they go out of scope
   // and the internal com::ptr releases its reference to the COM object
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="attach"></a>ptr::Attach

COM 개체를 연결 된 `com::ptr`합니다.

```cpp
void Attach(
   _interface_type * _right
);
```

### <a name="parameters"></a>매개 변수

*_right*<br/>
연결할 COM 인터페이스 포인터입니다.

### <a name="exceptions"></a>예외

경우는 `com::ptr` COM 개체에 대 한 참조를 이미 소유 `Attach` throw <xref:System.InvalidOperationException>합니다.

### <a name="remarks"></a>설명

에 대 한 호출 `Attach` COM 개체를 참조 하지만에 대 한 호출자의 참조를 해제 하지 않습니다.

전달 `NULL` 에 `Attach` 취해 아무 동작도 수행 합니다.

### <a name="example"></a>예제

이 예제에서는 `com::ptr`을 사용해서 해당 개인 멤버 `IXMLDOMDocument` 개체를 래핑하는 CLR 클래스를 구현합니다. `ReplaceDocument` 멤버 함수에 대 한 첫 번째 호출 `Release` 에서 이전에 소유한 개체와 호출 `Attach` 새 문서를 연결 합니다.

```cpp
// comptr_attach.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // replace currently held COM object with another one
   void ReplaceDocument(IXMLDOMDocument* pDoc) {
      // release current document object
      m_ptrDoc.Release();
      // attach the new document object
      m_ptrDoc.Attach(pDoc);
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that creates a raw XML DOM Document object
IXMLDOMDocument* CreateDocument() {
   IXMLDOMDocument* pDoc = NULL;
   Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
      CLSCTX_INPROC_SERVER, IID_IXMLDOMDocument, (void**)&pDoc));
   return pDoc;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // get another document object from unmanaged function and
      // store it in place of the one held by our ref class
      pDoc = CreateDocument();
      doc.ReplaceDocument(pDoc);
      // no further need for raw object reference
      pDoc->Release();
      pDoc = NULL;
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="createInstance"></a>ptr::CreateInstance

내에서 COM 개체의 인스턴스를 만듭니다를 `com::ptr`입니다.

```cpp
void CreateInstance(
   System::String ^ progid,
   LPUNKNOWN pouter,
   DWORD cls_context
);
void CreateInstance(
   System::String ^ progid,
   LPUNKNOWN pouter
);
void CreateInstance(
   System::String ^ progid
);
void CreateInstance(
   const wchar_t * progid,
   LPUNKNOWN pouter,
   DWORD cls_context
);
void CreateInstance(
   const wchar_t * progid,
   LPUNKNOWN pouter
);
void CreateInstance(
   const wchar_t * progid
);
void CreateInstance(
   REFCLSID rclsid,
   LPUNKNOWN pouter,
   DWORD cls_context
);
void CreateInstance(
   REFCLSID rclsid,
   LPUNKNOWN pouter
);
void CreateInstance(
   REFCLSID rclsid
);
```

### <a name="parameters"></a>매개 변수

*progid*<br/>
`ProgID` 문자열입니다.

*pouter*<br/>
집계 개체의 IUnknown 인터페이스 (controlling IUnknown)에 대 한 포인터입니다. 하는 경우 `pouter` 를 지정 하지 않으면 `NULL` 사용 됩니다.

*cls_context*<br/>
새로 만든된 개체를 관리 하는 코드가 실행 되는 컨텍스트. 값을 가져옵니다는 `CLSCTX` 열거형입니다. 경우 `cls_context` 를 지정 하지 않으면 CLSCTX_ALL 사용 되는 값입니다.

*rclsid*<br/>
`CLSID` 데이터 및 개체를 만드는 데 사용할 코드를 사용 하 여 연결 합니다.

### <a name="exceptions"></a>예외

경우는 `com::ptr` COM 개체에 대 한 참조를 이미 소유 `CreateInstance` throw <xref:System.InvalidOperationException>합니다.

이 함수 호출 `CoCreateInstance` 사용 하 여 <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> 오류 변환할 `HRESULT` 적절 한 예외에 합니다.

### <a name="remarks"></a>설명

`CreateInstance` 사용 하 여 `CoCreateInstance` ProgID 또는 CLSID에서 식별 된 지정된 된 개체의 새 인스턴스를 만들려고 합니다. `com::ptr` 새로 만든된 개체를 참조 하 고 소멸 시 모든 소유 참조를 자동으로 해제 됩니다.

### <a name="example"></a>예제

이 예제에서는 `com::ptr`을 사용해서 해당 개인 멤버 `IXMLDOMDocument` 개체를 래핑하는 CLR 클래스를 구현합니다. 클래스 생성자에 사용할 두 가지 다른 형태의 `CreateInstance` ProgID 또는 CLSID plus는 CLSCTX에서 문서 개체를 만들려고 합니다.

```cpp
// comptr_createinstance.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }
   XmlDocument(REFCLSID clsid, DWORD clsctx) {
      m_ptrDoc.CreateInstance(clsid, NULL, clsctx);
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   try {
      // create the class from a progid string
      XmlDocument doc1("Msxml2.DOMDocument.3.0");

      // or from a clsid with specific CLSCTX
      XmlDocument doc2(CLSID_DOMDocument30, CLSCTX_INPROC_SERVER);
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
}
```

## <a name="detach"></a>ptr::Detach

개체에 대 한 포인터를 반환 하는 COM 개체의 소유권을 포기 합니다.

```cpp
_interface_type * Detach();
```

### <a name="return-value"></a>반환 값

COM 개체에 대 한 포인터입니다.

개체가 없는 소유 하는 경우에 NULL이 반환 됩니다.

### <a name="exceptions"></a>예외

내부적으로 `QueryInterface` 소유 COM 개체 및 모든 오류 라고 `HRESULT` 하 여 예외를 변환할 때 <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>합니다.

### <a name="remarks"></a>설명

`Detach` 먼저 호출자를 대신 하 여 COM 개체에 대 한 참조를 추가 하 고 다음 소유 하는 모든 참조를 해제 합니다 `com::ptr`합니다.  호출자에 게 궁극적으로 반환된 된 개체 삭제를 릴리스해야 합니다.

### <a name="example"></a>예제

이 예제에서는 `com::ptr`을 사용해서 해당 개인 멤버 `IXMLDOMDocument` 개체를 래핑하는 CLR 클래스를 구현합니다.  합니다 `DetachDocument` 멤버 함수 호출 `Detach` COM 개체의 소유권을 호출자에 대 한 포인터를 반환 합니다.

```cpp
// comptr_detach.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // detach the COM object and return it
   // this releases the internal reference to the object
   IXMLDOMDocument* DetachDocument() {
      return m_ptrDoc.Detach();
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that loads XML into a raw XML DOM Document object
HRESULT LoadXml(IXMLDOMDocument* pDoc, BSTR bstrXml) {
   HRESULT hr = S_OK;
   VARIANT_BOOL bSuccess;
   hr = pDoc->loadXML(bstrXml, &bSuccess);
   if (S_OK == hr && !bSuccess) {
      hr = E_FAIL;
   }
   return hr;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;
   BSTR bstrXml = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      bstrXml = ::SysAllocString(L"<word>persnickety</word>");
      if (NULL == bstrXml) {
         throw gcnew OutOfMemoryException("bstrXml");
      }
      // detach the document object from the ref class
      pDoc = doc.DetachDocument();
      // use unmanaged function and raw object to load xml
      Marshal::ThrowExceptionForHR(LoadXml(pDoc, bstrXml));
      // release document object as the ref class no longer owns it
      pDoc->Release();
      pDoc = NULL;
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }

   }
}
```

## <a name="getInterface"></a>ptr::GetInterface

소유 COM 개체에 대 한 포인터를 반환합니다.

```cpp
_interface_type * GetInterface();
```

### <a name="return-value"></a>반환 값

소유 COM 개체에 대 한 포인터입니다.

### <a name="exceptions"></a>예외

내부적으로 `QueryInterface` 소유 COM 개체 및 모든 오류 라고 `HRESULT` 하 여 예외를 변환할 때 <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>합니다.

### <a name="remarks"></a>설명

`com::ptr` 호출자를 대신 하 여 COM 개체에 대 한 참조를 추가 하 고 COM 개체에 대 한 자체 참조를 유지 합니다. 호출자에 게 반환된 된 개체에 대 한 참조를 릴리스해야 궁극적으로 또는 소멸 되지 않습니다.

### <a name="example"></a>예제

이 예제에서는 `com::ptr`을 사용해서 해당 개인 멤버 `IXMLDOMDocument` 개체를 래핑하는 CLR 클래스를 구현합니다. 합니다 `GetDocument` 멤버 함수를 사용 하 여 `GetInterface` COM 개체에 대 한 포인터를 반환 합니다.

```cpp
// comptr_getinterface.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // add a reference to and return the COM object
   // but keep an internal reference to the object
   IXMLDOMDocument* GetDocument() {
      return m_ptrDoc.GetInterface();
   }

   // simplified function that only writes the first node
   void WriteDocument() {
      IXMLDOMNode* pNode = NULL;
      BSTR bstr = NULL;

      try {
         // use operator -> to call XML Doc member
         Marshal::ThrowExceptionForHR(m_ptrDoc->get_firstChild(&pNode));
         if (NULL != pNode) {
            // write out the xml
            Marshal::ThrowExceptionForHR(pNode->get_nodeName(&bstr));
            String^ strName = gcnew String(bstr);
            Console::Write("<{0}>", strName);
            ::SysFreeString(bstr);
            bstr = NULL;

            Marshal::ThrowExceptionForHR(pNode->get_text(&bstr));
            Console::Write(gcnew String(bstr));
            ::SysFreeString(bstr);
            bstr = NULL;

            Console::WriteLine("</{0}>", strName);
         }
      }
      finally {
         if (NULL != pNode) {
            pNode->Release();
         }
         ::SysFreeString(bstr);
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that loads XML into a raw XML DOM Document object
HRESULT LoadXml(IXMLDOMDocument* pDoc, BSTR bstrXml) {
   HRESULT hr = S_OK;
   VARIANT_BOOL bSuccess;
   hr = pDoc->loadXML(bstrXml, &bSuccess);
   if (S_OK == hr && !bSuccess) {
      hr = E_FAIL;
   }
   return hr;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;
   BSTR bstrXml = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      bstrXml = ::SysAllocString(L"<word>persnickety</word>");
      if (NULL == bstrXml) {
         throw gcnew OutOfMemoryException("bstrXml");
      }
      // detach the document object from the ref class
      pDoc = doc.GetDocument();
      // use unmanaged function and raw object to load xml
      Marshal::ThrowExceptionForHR(LoadXml(pDoc, bstrXml));
      // release reference to document object (but ref class still references it)
      pDoc->Release();
      pDoc = NULL;

      // call another function on the ref class
      doc.WriteDocument();
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }

   }
}
```

```Output
<word>persnickety</word>
```

## <a name="queryInterface"></a>ptr::QueryInterface

인터페이스에 대 한 소유 COM 개체를 쿼리하고 결과를 다른 연결 `com::ptr`합니다.

```cpp
template<class _other_type>
void QueryInterface(
   ptr<_other_type> % other
);
```

### <a name="parameters"></a>매개 변수

*other*<br/>
`com::ptr` 는 인터페이스를 받습니다.

### <a name="exceptions"></a>예외

내부적으로 `QueryInterface` 소유 COM 개체 및 모든 오류 라고 `HRESULT` 하 여 예외를 변환할 때 <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>합니다.

### <a name="remarks"></a>설명

현재 래퍼를 소유 하는 COM 개체의 다른 인터페이스에 대 한 COM 래퍼를 만들려면이 메서드를 사용 합니다. 이 메서드를 호출 `QueryInterface` COM의 특정 인터페이스에 대 한 포인터를 요청 하려면 소유 COM 개체를 통해 개체 및 전달 기능에 대 한 반환 된 인터페이스 포인터를 연결 `com::ptr`합니다.

### <a name="example"></a>예제

이 예제에서는 `com::ptr`을 사용해서 해당 개인 멤버 `IXMLDOMDocument` 개체를 래핑하는 CLR 클래스를 구현합니다. `WriteTopLevelNode` 멤버 함수를 사용 하 여 `QueryInterface` 로컬에 맞게 `com::ptr` 사용 하 여를 `IXMLDOMNode` 다음 전달는 `com::ptr` (추적 참조)에서 노드의 이름 및 텍스트 속성을 콘솔에 작성 하는 private 멤버 함수에 합니다.

```cpp
// comptr_queryinterface.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   void LoadXml(String^ xml) {
      pin_ptr<const wchar_t> pinnedXml = PtrToStringChars(xml);
      BSTR bstr = NULL;

      try {
         // load some XML into our document
         bstr = ::SysAllocString(pinnedXml);
         if (NULL == bstr) {
            throw gcnew OutOfMemoryException;
         }
         VARIANT_BOOL bIsSuccessful = false;
         // use operator -> to call IXMODOMDocument member function
         Marshal::ThrowExceptionForHR(m_ptrDoc->loadXML(bstr, &bIsSuccessful));
      }
      finally {
         ::SysFreeString(bstr);
      }
   }

   // write the top level node to the console
   void WriteTopLevelNode() {
      com::ptr<IXMLDOMNode> ptrNode;

      // query for the top level node interface
      m_ptrDoc.QueryInterface(ptrNode);
      WriteNode(ptrNode);
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   // simplified function that only writes the node
   void WriteNode(com::ptr<IXMLDOMNode> % node) {
      BSTR bstr = NULL;

      try {
         // write out the name and text properties
         Marshal::ThrowExceptionForHR(node->get_nodeName(&bstr));
         String^ strName = gcnew String(bstr);
         Console::Write("<{0}>", strName);
         ::SysFreeString(bstr);
         bstr = NULL;

         Marshal::ThrowExceptionForHR(node->get_text(&bstr));
         Console::Write(gcnew String(bstr));
         ::SysFreeString(bstr);
         bstr = NULL;

         Console::WriteLine("</{0}>", strName);
      }
      finally {
         ::SysFreeString(bstr);
      }
   }

   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // stream some xml into the document
      doc.LoadXml("<word>persnickety</word>");

      // write the document to the console
      doc.WriteTopLevelNode();
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
}
```

```Output
<#document>persnickety</#document>
```

## <a name="release"></a>ptr::Release

COM 개체에 대 한 모든 소유 참조를 해제합니다.

```cpp
void Release();
```

### <a name="remarks"></a>설명

COM 개체에서 모든 소유 참조를 해제 하 고 COM 개체에 내부 핸들을 설정 합니다.이 함수를 호출 `nullptr`합니다.  COM 개체에 다른 참조가 있으면 제거 됩니다.

### <a name="example"></a>예제

이 예제에서는 `com::ptr`을 사용해서 해당 개인 멤버 `IXMLDOMDocument` 개체를 래핑하는 CLR 클래스를 구현합니다.  `ReplaceDocument` 멤버 함수를 사용 하 여 `Release` 새 문서에 연결 하기 전에 모든 이전 문서 개체를 해제 합니다.

```cpp
// comptr_release.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // replace currently held COM object with another one
   void ReplaceDocument(IXMLDOMDocument* pDoc) {
      // release current document object
      m_ptrDoc.Release();
      // attach the new document object
      m_ptrDoc.Attach(pDoc);
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that creates a raw XML DOM Document object
IXMLDOMDocument* CreateDocument() {
   IXMLDOMDocument* pDoc = NULL;
   Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
      CLSCTX_INPROC_SERVER, IID_IXMLDOMDocument, (void**)&pDoc));
   return pDoc;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // get another document object from unmanaged function and
      // store it in place of the one held by our ref class
      pDoc = CreateDocument();
      doc.ReplaceDocument(pDoc);
      // no further need for raw object reference
      pDoc->Release();
      pDoc = NULL;
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="operator-arrow"></a>ptr::operator-&gt;

멤버 액세스 연산자를 소유 하는 COM 개체에서 메서드를 호출 하는 데 사용 합니다.

```cpp
_detail::smart_com_ptr<_interface_type> operator->();
```

### <a name="return-value"></a>반환 값

`smart_com_ptr` COM 개체에 있습니다.

### <a name="exceptions"></a>예외

내부적으로 `QueryInterface` 소유 COM 개체 및 모든 오류 라고 `HRESULT` 하 여 예외를 변환할 때 <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>합니다.

### <a name="remarks"></a>설명

이 연산자를 사용 하면 소유 COM 개체의 메서드를 호출할 수 있습니다. 임시 반환 `smart_com_ptr` 자동으로 처리 하는 자체 `AddRef` 고 `Release`입니다.

### <a name="example"></a>예제

이 예제에서는 `com::ptr`을 사용해서 해당 개인 멤버 `IXMLDOMDocument` 개체를 래핑하는 CLR 클래스를 구현합니다. 합니다 `WriteDocument` 함수는 `operator->` 를 호출 하는 `get_firstChild` 문서 개체의 멤버입니다.

```cpp
// comptr_op_member.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // add a reference to and return the COM object
   // but keep an internal reference to the object
   IXMLDOMDocument* GetDocument() {
      return m_ptrDoc.GetInterface();
   }

   // simplified function that only writes the first node
   void WriteDocument() {
      IXMLDOMNode* pNode = NULL;
      BSTR bstr = NULL;

      try {
         // use operator -> to call XML Doc member
         Marshal::ThrowExceptionForHR(m_ptrDoc->get_firstChild(&pNode));
         if (NULL != pNode) {
            // write out the xml
            Marshal::ThrowExceptionForHR(pNode->get_nodeName(&bstr));
            String^ strName = gcnew String(bstr);
            Console::Write("<{0}>", strName);
            ::SysFreeString(bstr);
            bstr = NULL;

            Marshal::ThrowExceptionForHR(pNode->get_text(&bstr));
            Console::Write(gcnew String(bstr));
            ::SysFreeString(bstr);
            bstr = NULL;

            Console::WriteLine("</{0}>", strName);
         }
      }
      finally {
         if (NULL != pNode) {
            pNode->Release();
         }
         ::SysFreeString(bstr);
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that loads XML into a raw XML DOM Document object
HRESULT LoadXml(IXMLDOMDocument* pDoc, BSTR bstrXml) {
   HRESULT hr = S_OK;
   VARIANT_BOOL bSuccess;
   hr = pDoc->loadXML(bstrXml, &bSuccess);
   if (S_OK == hr && !bSuccess) {
      hr = E_FAIL;
   }
   return hr;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;
   BSTR bstrXml = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      bstrXml = ::SysAllocString(L"<word>persnickety</word>");
      if (NULL == bstrXml) {
         throw gcnew OutOfMemoryException("bstrXml");
      }
      // detach the document object from the ref class
      pDoc = doc.GetDocument();
      // use unmanaged function and raw object to load xml
      Marshal::ThrowExceptionForHR(LoadXml(pDoc, bstrXml));
      // release reference to document object (but ref class still references it)
      pDoc->Release();
      pDoc = NULL;

      // call another function on the ref class
      doc.WriteDocument();
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }

   }
}
```

```Output
<word>persnickety</word>
```

## <a name="operator-assign"></a>ptr::operator=

COM 개체를 연결 된 `com::ptr`합니다.

```cpp
ptr<_interface_type> % operator=(
   _interface_type * _right
);
```

### <a name="parameters"></a>매개 변수

*_right*<br/>
연결할 COM 인터페이스 포인터입니다.

### <a name="return-value"></a>반환 값

에 대 한 추적 참조는 `com::ptr`합니다.

### <a name="exceptions"></a>예외

경우는 `com::ptr` COM 개체에 대 한 참조를 이미 소유 `operator=` throw <xref:System.InvalidOperationException>합니다.

### <a name="remarks"></a>설명

COM 개체를 할당 한 `com::ptr` COM 개체를 참조 하지만에 대 한 호출자의 참조를 해제 하지 않습니다.

이 연산자는 것과 동일한 효과가 `Attach`합니다.

### <a name="example"></a>예제

이 예제에서는 `com::ptr`을 사용해서 해당 개인 멤버 `IXMLDOMDocument` 개체를 래핑하는 CLR 클래스를 구현합니다.  `ReplaceDocument` 멤버 함수에 대 한 첫 번째 호출 `Release` 에 소유 했던 개체와 사용 하 여 `operator=` 새 문서를 연결 합니다.

```cpp
// comptr_op_assign.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // replace currently held COM object with another one
   void ReplaceDocument(IXMLDOMDocument* pDoc) {
      // release current document object
      m_ptrDoc.Release();
      // attach the new document object
      m_ptrDoc = pDoc;
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that creates a raw XML DOM Document object
IXMLDOMDocument* CreateDocument() {
   IXMLDOMDocument* pDoc = NULL;
   Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
      CLSCTX_INPROC_SERVER, IID_IXMLDOMDocument, (void**)&pDoc));
   return pDoc;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // get another document object from unmanaged function and
      // store it in place of the one held by the ref class
      pDoc = CreateDocument();
      doc.ReplaceDocument(pDoc);
      // no further need for raw object reference
      pDoc->Release();
      pDoc = NULL;
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="operator-bool"></a> ptr::operator bool

연산자를 사용 하 여 `com::ptr` 조건식에서입니다.

```cpp
operator bool();
```

### <a name="return-value"></a>반환 값

`true` 소유 COM 개체가 잘못 되었습니다. `false` 그렇지 않은 경우.

### <a name="remarks"></a>설명

소유 COM 개체가 없는 경우 올바른 `nullptr`합니다.

이 연산자를 변환 `_detail_class::_safe_bool` 는 보다 안전한 `bool` 정수 계열 형식으로 변환할 수 없기 때문입니다.

### <a name="example"></a>예제

이 예제에서는 `com::ptr`을 사용해서 해당 개인 멤버 `IXMLDOMDocument` 개체를 래핑하는 CLR 클래스를 구현합니다. 합니다 `CreateInstance` 멤버 함수를 사용 하 여 `operator bool` 경우 유효 하 고 콘솔에 작성 하는 경우를 확인 하려면 새 문서 개체를 만든 후 합니다.

```cpp
// comptr_op_bool.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   void CreateInstance(String^ progid) {
      if (!m_ptrDoc) {
         m_ptrDoc.CreateInstance(progid);
         if (m_ptrDoc) { // uses operator bool
            Console::WriteLine("DOM Document created.");
         }
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   try {
      XmlDocument doc;
      // create the instance from a progid string
      doc.CreateInstance("Msxml2.DOMDocument.3.0");
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
}
```

```Output
DOM Document created.
```

## <a name="operator-logical-not"></a>ptr::operator!

소유 하는 COM 개체 잘못 인지 확인 하는 연산자입니다.

```cpp
bool operator!();
```

### <a name="return-value"></a>반환 값

`true` 소유 COM 개체가 잘못 된 경우 `false` 그렇지 않은 경우.

### <a name="remarks"></a>설명

소유 COM 개체가 없는 경우 올바른 `nullptr`합니다.

### <a name="example"></a>예제

이 예제에서는 `com::ptr`을 사용해서 해당 개인 멤버 `IXMLDOMDocument` 개체를 래핑하는 CLR 클래스를 구현합니다.  합니다 `CreateInstance` 멤버 함수를 사용 하 여 `operator!` 문서 개체를 이미 소유 및 개체가 유효 하지 않은 경우에 새 인스턴스를 만듭니다를 판단 합니다.

```cpp
// comptr_op_not.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   void CreateInstance(String^ progid) {
      if (!m_ptrDoc) {
         m_ptrDoc.CreateInstance(progid);
         if (m_ptrDoc) {
            Console::WriteLine("DOM Document created.");
         }
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   try {
      XmlDocument doc;
      // create the instance from a progid string
      doc.CreateInstance("Msxml2.DOMDocument.3.0");
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
}
```

```Output
DOM Document created.
```
