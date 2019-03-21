---
title: '&lt;paramref > (c + + 문서 주석)'
ms.date: 11/04/2016
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- paramref C++ XML tag
- <paramref> C++ XML tag
ms.assetid: c5730dc2-7159-421f-b2d5-bb971e307122
ms.openlocfilehash: cee35ddb5fd5cd811e45f0aa49e94dd9c4b8b180
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826772"
---
# <a name="ltparamrefgt"></a>&lt;paramref&gt;

\<paramref > 태그를 사용하여 단어가 매개 변수임을 나타낼 수 있습니다. .xml 파일을 처리하여 이 매개 변수의 형식을 고유하게 지정할 수 있습니다.

## <a name="syntax"></a>구문

```
<paramref name="name"/>
```

#### <a name="parameters"></a>매개 변수

*name*<br/>
참조할 매개 변수의 이름입니다.  이름을 단일 또는 이중 따옴표로 묶습니다.  
  `name`가 검색되지 않는 경우 컴파일러에서 경고가 발생합니다.

## <a name="remarks"></a>설명

[/doc](doc-process-documentation-comments-c-cpp.md)로 컴파일하여 문서 주석을 파일로 처리합니다.

## <a name="example"></a>예제

```
// xml_paramref_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_paramref_tag.dll
/// Text for class MyClass.
public ref class MyClass {
   /// <summary>MyMethod is a method in the MyClass class.
   /// The <paramref name="Int1"/> parameter takes a number.
   /// </summary>
   void MyMethod(int Int1) {}
};
```

## <a name="see-also"></a>참고자료

[XML 문서](xml-documentation-visual-cpp.md)
