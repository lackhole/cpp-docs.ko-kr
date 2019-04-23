---
title: 메서드 특성 (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- method attributes
- attributes [C++/CLI], reference topics
ms.assetid: b2313352-480d-488b-8c35-6242ffd3a549
ms.openlocfilehash: aa67d45dfc0fadd300caeaaeb8a7c25bb1c38bcb
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59023570"
---
# <a name="method-attributes"></a>메서드 특성

다음과 같은 특성, coclass 등 클래스나 인터페이스의 메서드에 적용 됩니다.

|특성|설명|
|---------------|-----------------|
|[bindable](bindable.md)|속성이 데이터 바인딩을 지원합니다.|
|[call_as](call-as.md)|사용 불가능 한 함수를 원격 함수에 매핑할 수 있습니다.|
|[custom](custom-cpp.md)|고유한 특성을 정의할 수 있습니다.|
|[db_column](db-column.md)|행 집합에 지정된 된 열을 바인딩합니다.|
|[db_command](db-command.md)|OLE DB 명령을 만듭니다.|
|[db_param](db-param.md)|입력 또는 출력 매개 변수를 사용 하 여 지정 된 멤버 변수를 연결 하 고 변수를 구분 합니다.|
|[db_source](db-source.md)|데이터 원본에 연결을 만듭니다.|
|[db_table](db-table.md)|OLE DB 테이블을 엽니다.|
|[defaultbind](defaultbind.md)|개체를 가장 잘 나타내는 단일, 바인딩 가능한 속성을 나타냅니다.|
|[defaultcollelem](defaultcollelem.md)|Visual Basic 코드 최적화를 위해 사용 합니다.|
|[displaybind](displaybind.md)|바인딩 가능한 사용자에 게 표시 하는 속성을 나타냅니다.|
|[helpcontext](helpcontext.md)|이 요소에 대 한 정보를 볼 수 있는 컨텍스트 ID를 지정 합니다 **도움말** 파일입니다.|
|[helpfile](helpfile.md)|이름을 가져오거나 설정 합니다 **도움말** 형식 라이브러리 파일입니다.|
|[helpstring](helpstring.md)|적용되는 요소를 설명하는 데 사용되는 문자열을 지정합니다.|
|[helpstringcontext](helpstringcontext.md)|.hlp 또는.chm 파일에서 도움말 항목의 ID를 지정합니다.|
|[helpstringdll](helpstringdll.md)|문서 문자열 조회 (지역화)를 수행 하는 데 DLL의 이름을 지정 합니다.|
|[hidden](hidden.md)|항목이 있지만 하지 사용자 기반 브라우저에 표시할지를 나타냅니다.|
|[ID](id.md)|멤버 함수 (속성 또는 메서드를 인터페이스나 dispinterface)에 대 한 DISPID를 지정합니다.|
|[immediatebind](immediatebind.md)|데이터베이스는 즉시 알림을 받을 수는 데이터 바인딩된 개체의 속성에는 모든 변경 내용을 나타냅니다.|
|[in](in-cpp.md)|매개 변수가 호출된 된 프로시저를 호출 하는 프로시저에서 전달할 임을 나타냅니다.|
|[local](local-cpp.md)|MIDL 컴파일러 인터페이스 헤더에 사용 되는 경우에 헤더 생성기로 사용할 수 있습니다. 개별 함수를 사용할 경우 없는 스텁 생성 되는 로컬 프로시저를 지정 합니다.|
|[nonbrowsable](nonbrowsable.md)|인터페이스 멤버를 속성 브라우저에 표시 되지 해야 나타냅니다.|
|[propget](propget.md)|속성 접근자 함수를 지정합니다.|
|[propput](propput.md)|속성 설정 함수를 지정합니다.|
|[propputref](propputref.md)|값 대신 참조를 사용 하는 속성 설정 함수를 지정 합니다.|
|[ptr](ptr.md)|전체 포인터에 대 한 포인터를 지정합니다.|
|[range](range-cpp.md)|인수 값은 런타임에 설정 된 필드에 허용 되는 값의 범위를 지정 합니다.|
|[requestedit](requestedit.md)|속성이 `OnRequestEdit` 알림을 지원함을 나타냅니다.|
|[restricted](restricted.md)|모듈, 인터페이스 또는 dispinterface의 멤버를 임의로 호출할 수 없습니다 지정 합니다.|
|[satype](satype.md)|데이터 형식을 지정 합니다 `SAFEARRAY` 구조입니다.|
|[source](source-cpp.md)|클래스에 연결 지점에 대 한 컨트롤의 소스 인터페이스를 지정합니다. 메서드나 속성에는 `source` 특성 멤버에서 개체 또는 이벤트의 소스인는 VARIANT를 반환 함을 나타냅니다.|
|[synchronize](synchronize.md)|대상 메서드에 대 한 액세스를 동기화합니다.|
|[vararg](vararg.md)|함수 인수의 변수 번호를 지정 합니다.|

## <a name="see-also"></a>참고자료

[용도별 특성](attributes-by-usage.md)