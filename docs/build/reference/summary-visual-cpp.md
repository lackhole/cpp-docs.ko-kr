---
title: '&lt;요약 > (c + + 문서 주석)'
ms.date: 11/04/2016
f1_keywords:
- <summary>
- summary
helpviewer_keywords:
- <summary> C++ XML tag
- summary C++ XML tag
ms.assetid: cdeeefbb-1339-45d6-9002-10042a9a2726
ms.openlocfilehash: 68bb8b7c269b3406438e5cf21dde7179f7e67646
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826577"
---
# <a name="ltsummarygt"></a>&lt;요약&gt;

\<summary > 태그를 사용하여 형식 또는 형식 멤버를 설명해야 합니다. [\<remarks>](remarks-visual-cpp.md)를 사용하여 형식 설명에 보충 정보를 추가할 수 있습니다.

## <a name="syntax"></a>구문

```
<summary>description</summary>
```

#### <a name="parameters"></a>매개 변수

*description*<br/>
개체에 대한 요약입니다.

## <a name="remarks"></a>설명

\<summary> 태그의 텍스트는 IntelliSense의 형식에 대한 유일한 정보 소스이며 [개체 브라우저](/visualstudio/ide/viewing-the-structure-of-code) 및 코드 주석 웹 보고서에도 표시됩니다.

[/doc](doc-process-documentation-comments-c-cpp.md)로 컴파일하여 문서 주석을 파일로 처리합니다.

## <a name="example"></a>예제

```
// xml_summary_tag.cpp
// compile with: /LD /clr /doc
// post-build command: xdcmake xml_summary_tag.dll

/// Text for class MyClass.
public ref class MyClass {
public:
   /// <summary>MyMethod is a method in the MyClass class.
   /// <para>Here's how you could make a second paragraph in a description. <see cref="System::Console::WriteLine"/> for information about output statements.</para>
   /// <seealso cref="MyClass::MyMethod2"/>
   /// </summary>
   void MyMethod(int Int1) {}

   /// text
   void MyMethod2() {}
};
```

## <a name="see-also"></a>참고자료

[XML 문서](xml-documentation-visual-cpp.md)
