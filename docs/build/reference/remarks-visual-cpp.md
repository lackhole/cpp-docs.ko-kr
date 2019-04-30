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
ms.openlocfilehash: 0d0c63d55de80f498498a6873dacb5e83fc956b7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319163"
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

## <a name="remarks"></a>설명

[/doc](doc-process-documentation-comments-c-cpp.md)로 컴파일하여 문서 주석을 파일로 처리합니다.

## <a name="example"></a>예제

```
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

## <a name="see-also"></a>참고자료

[XML 문서](xml-documentation-visual-cpp.md)
