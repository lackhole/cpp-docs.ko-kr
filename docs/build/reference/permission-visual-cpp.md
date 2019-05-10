---
title: '&lt;사용 권한 > (C++ 문서 주석)'
ms.date: 11/04/2016
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C++ XML tag
- permission C++ XML tag
ms.assetid: 537ee2bc-95bd-48e4-9ce6-3420c3da87f4
ms.openlocfilehash: 764048f7bc579afa6862bdff40968588955dc307
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319943"
---
# <a name="ltpermissiongt"></a>&lt;permission&gt;

\<permission> 태그를 사용하면 멤버 액세스 권한을 문서화할 수 있습니다. <xref:System.Security.PermissionSet>를 사용하면 멤버 액세스 권한을 지정할 수 있습니다.

## <a name="syntax"></a>구문

```
<permission cref="member">description</permission>
```

#### <a name="parameters"></a>매개 변수

*member*<br/>
현재 컴파일 환경에서 호출할 수 있는 멤버 또는 필드에 대한 참조입니다. 컴파일러는 지정된 코드 요소가 있으며 `member`를 출력 XML의 정식 요소 이름으로 변환하는지 확인합니다.  이름을 단일 또는 이중 따옴표로 묶습니다.

`member`가 검색되지 않는 경우 컴파일러에서 경고가 발생합니다.

제네릭 형식에 대한 cref 참조를 만드는 방법에 대한 자세한 내용은 [\<see>](see-visual-cpp.md)를 참조하세요.

*description*<br/>
멤버 액세스 권한에 대한 설명입니다.

## <a name="remarks"></a>설명

[/doc](doc-process-documentation-comments-c-cpp.md)로 컴파일하여 문서 주석을 파일로 처리합니다.

MSVC 컴파일러는 문서 주석을 통해 단일 패스로 cref 참조를 확인 하려고 합니다.  따라서 C++ 조회 규칙을 사용하는 경우 컴파일러에서 기호를 찾을 수 없으며 참조는 확인되지 않음으로 표시됩니다. 자세한 내용은 [\<seealso>](seealso-visual-cpp.md)를 참조하세요.

## <a name="example"></a>예제

```
// xml_permission_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_permission_tag.dll
using namespace System;
/// Text for class TestClass.
public ref class TestClass {
   /// <permission cref="System::Security::PermissionSet">Everyone can access this method.</permission>
   void Test() {}
};
```

## <a name="see-also"></a>참고자료

[XML 문서](xml-documentation-visual-cpp.md)
