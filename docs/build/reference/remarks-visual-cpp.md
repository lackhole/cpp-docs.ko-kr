---
title: '&lt;설명 > (C++ 문서 주석)'
ms.date: 11/04/2016
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- <remarks> C++ XML tag
- remarks C++ XML tag
ms.assetid: c820083b-3192-40ab-9ec8-1472c55b4247
ms.openlocfilehash: 096280526b12feff33377a705f7c03548a1f0f13
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988654"
---
# <a name="ltremarksgt"></a>&lt;설명&gt;

\<remarks> 태그는 형식에 대한 정보를 추가하여 [\<summary>](summary-visual-cpp.md)로 지정된 정보를 보완하기 위해 사용됩니다. 이 정보는 [개체 브라우저](/visualstudio/ide/viewing-the-structure-of-code) 및 코드 주석 웹 보고서에 표시됩니다.

## <a name="syntax"></a>구문

```
<remarks>description</remarks>
```

#### <a name="parameters"></a>매개 변수

*description*<br/>
멤버에 대한 설명입니다.

## <a name="remarks"></a>주의

[/doc](doc-process-documentation-comments-c-cpp.md)로 컴파일하여 문서 주석을 파일로 처리합니다.

## <a name="example"></a>예제

```cpp
// xml_remarks_tag.cpp
// compile with: /LD /clr /doc
// post-build command: xdcmake xml_remarks_tag.dll

using namespace System;

/// <summary>
/// You may have some primary information about this class.
/// </summary>
/// <remarks>
/// You may have some additional information about this class.
/// </remarks>
public ref class MyClass {};
```

## <a name="see-also"></a>참조

[XML 문서](xml-documentation-visual-cpp.md)
