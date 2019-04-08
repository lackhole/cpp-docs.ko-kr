---
title: 인터페이스 특성 (c + + COM)
ms.date: 10/02/2018
helpviewer_keywords:
- attributes [C++/CLI], reference topics
- interface attributes
ms.assetid: 27fcdfee-abce-4585-8b53-ee31635356e8
ms.openlocfilehash: 8218ccb66c6be9edef5d7de751a73bf4753d069f
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59027207"
---
# <a name="interface-attributes"></a>인터페이스 특성

다음 특성을 적용 합니다 [인터페이스 (또는 __interface)](../../cpp/interface.md) c + + 키워드입니다.

|특성|설명|
|---------------|-----------------|
|[async_uuid](async-uuid.md)|MIDL 컴파일러에 지시 합니다 COM 인터페이스의 동기 및 비동기 버전을 정의 하는 UUID를 지정 합니다.|
|[사용자 지정](custom-cpp.md)|사용자 지정 특성을 정의할 수 있습니다.|
|[dispinterface](dispinterface.md)|.Idl 파일의 인터페이스를 디스패치 인터페이스로 배치합니다.|
|[dual](dual.md)|.Idl 파일에 이중 인터페이스와 인터페이스를 배치합니다.|
|[내보내기](export.md)|.Idl 파일에 배치할 데이터 구조를 하면 됩니다.|
|[helpcontext](helpcontext.md)|도움말 파일에서이 요소에 대 한 정보를 볼 수 있는 컨텍스트 ID를 지정 합니다.|
|[helpfile](helpfile.md)|형식 라이브러리에 대 한 도움말 파일의 이름을 설정합니다.|
|[helpstring](helpstring.md)|적용되는 요소를 설명하는 데 사용되는 문자열을 지정합니다.|
|[helpstringcontext](helpstringcontext.md)|.hlp 또는.chm 파일에서 도움말 항목의 ID를 지정합니다.|
|[typelib](helpstringdll.md)|문서 문자열 조회 (지역화)를 수행 하는 데 DLL의 이름을 지정 합니다.|
|[hidden](hidden.md)|항목이 있지만 하지 사용자 기반 브라우저에 표시할지를 나타냅니다.|
|[library_block](library-block.md)|.Idl 파일의 라이브러리 블록 내부 구문을 배치합니다.|
|[로컬](local-cpp.md)|MIDL 컴파일러 인터페이스 헤더에 사용 되는 경우에 헤더 생성기로 사용할 수 있습니다. 개별 함수를 사용할 경우 없는 스텁 생성 되는 로컬 프로시저를 지정 합니다.|
|[nonextensible](nonextensible.md)|지정 된 `IDispatch` 구현 속성만 포함 하 고 메서드 인터페이스 설명에 나열 된 런타임 시 추가 멤버를 사용 하 여 확장할 수 없습니다. 이 특성에만 유효는 [이중](dual.md) 인터페이스입니다.|
|[odl](odl.md)|개체 설명 언어 (ODL) 인터페이스는 인터페이스를 식별합니다.|
|[object](object-cpp.md)|사용자 지정 인터페이스를 식별합니다.|
|[oleautomation](oleautomation.md)|Automation 호환 인터페이스를 나타냅니다.|
|[pointer_default](pointer-default.md)|매개 변수 목록에 표시 되는 최상위 포인터를 제외 하 고 모든 포인터에 대 한 기본 포인터 특성을 지정 합니다.|
|[ptr](ptr.md)|전체 포인터에 대 한 포인터를 지정합니다.|
|[restricted](restricted.md)|라이브러리의 멤버를 임의로 호출할 수 없습니다 지정 합니다.|
|[uuid](uuid-cpp-attributes.md)|라이브러리에 대 한 고유 ID를 제공합니다.|

인터페이스를 정의 하는 것에 대 한 이러한 규칙을 준수 해야 합니다.

- 기본 호출 규칙은 [__stdcall](../../cpp/stdcall.md)합니다.

- 텍스트를 제공 하지 않는 경우 GUID는 제공 됩니다.

- 오버 로드 된 메서드가 허용 됩니다.

지정 하지 않는 경우는 [uuid](uuid-cpp-attributes.md) 특성 및 다른 특성 프로젝트 동일한 인터페이스 이름을 사용 하 여, 동일한 GUID가 생성 됩니다.

## <a name="see-also"></a>참고자료

[용도별 특성](attributes-by-usage.md)