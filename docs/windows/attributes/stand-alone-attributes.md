---
title: 독립 실행형 특성 (c + + COM)
ms.date: 10/02/2018
helpviewer_keywords:
- standalone attributes
- attributes [C++/CLI], standalone
ms.assetid: 0d72e84e-236c-43b3-ac9a-d9b91fcd6794
ms.openlocfilehash: 7dd1f35add3b23dbd81e32a1600481eec79fe7d7
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59033061"
---
# <a name="stand-alone-attributes"></a>독립 실행형 특성

독립 실행형 특성을 c + + 키워드에서 작동 하지 않습니다 하지만 코드 줄에 비슷합니다. 독립 실행형 특성 문은 줄의 끝에 세미콜론이 필요합니다.

## <a name="stand-alone-attribute-list"></a>독립 실행형 특성 목록

|특성|설명|
|---------------|-----------------|
|[cpp_quote](cpp-quote.md)|생성된 된 헤더 파일의 따옴표 없이 지정된 된 문자열을 내보냅니다.|
|[사용자 지정](custom-cpp.md)|고유한 특성을 정의할 수 있습니다.|
|[db_command](db-command.md)|OLE DB 명령을 만듭니다.|
|[emitidl](emitidl.md)|모든 후속 IDL 특성 처리 되어 생성된 된.idl 파일에 배치 될 지 여부를 결정 합니다.|
|[idl_module](idl-module.md)|DLL에 진입점을 지정합니다.|
|[idl_quote](idl-quote.md)|Visual c + +의 현재 버전에서 지원 되지 않는 IDL 구문을 사용할 수 있습니다 하 고 생성된 된.idl 파일을 통과 하도록 합니다.|
|[import](import.md)|주.idl 파일에서 참조 하려는 정의 포함 하는 다른.idl,.odl, 또는.h 파일을 지정 합니다.|
|[importidl](importidl.md)|생성된 된.idl 파일에 지정 된.idl 파일 삽입|
|[importlib](importlib.md)|다른 형식 라이브러리에 이미 컴파일된 형식을 만들고 있는 형식 라이브러리에서 사용할 수 있도록 합니다.|
|[include](include-cpp.md)|생성된 된.idl 파일에 포함할 하나 이상의 헤더 파일을 지정 합니다.|
|[includelib](includelib-cpp.md)|생성된 된.idl 파일에 포함 될.idl 또는.h 파일을 사용 하면 됩니다.|
|[library_block](library-block.md)|.Idl 파일의 라이브러리 블록 내부 구문을 배치합니다.|
|[name](module-cpp.md)|.Idl 파일의 라이브러리 블록을 정의합니다.|
|[no_injected_text](no-injected-text.md)|컴파일러 특성 사용으로 인해 코드를 삽입 하지 못하도록 방지 합니다.|
|[pragma](pragma.md)|생성된 된.idl 파일의 따옴표 없이 지정된 된 문자열을 내보냅니다.|

## <a name="see-also"></a>참고자료

[용도별 특성](attributes-by-usage.md)