---
title: Typedef, Enum, Union 및 Struct 특성 (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- union attributes
- attributes [C++/CLI], reference topics
ms.assetid: f8a4fe94-dc02-4aed-bc31-3e500d42f4c7
ms.openlocfilehash: 2b56ada13a0c597866d538991ed1e83078924ac9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407226"
---
# <a name="typedef-enum-union-and-struct-attributes"></a>Typedef, Enum, Union 및 Struct 특성

다음 특성을 적용 합니다 [typedef](../../cpp/aliases-and-typedefs-cpp.md), [구조체](../../cpp/struct-cpp.md), 및 [열거형](../../cpp/enumerations-cpp.md) C++ 키워드입니다.

### <a name="typedef"></a>형식 정의

|특성|설명|
|---------------|-----------------|
|[case](case-cpp.md)|사용 된 [switch_type](switch-type.md) 특성을 **union**합니다.|
|[custom](custom-cpp.md)|고유한 특성을 정의할 수 있습니다.|
|[export](export.md)|.Idl 파일에 배치할 데이터 구조를 하면 됩니다.|
|[first_is](first-is.md)|전송할 첫 번째 배열 요소의 인덱스를 지정 합니다.|
|[helpcontext](helpcontext.md)|도움말 파일에서이 요소에 대 한 정보를 볼 수 있는 컨텍스트 ID를 지정 합니다.|
|[helpfile](helpfile.md)|형식 라이브러리에 대 한 도움말 파일의 이름을 설정합니다.|
|[helpstring](helpstring.md)|적용되는 요소를 설명하는 데 사용되는 문자열을 지정합니다.|
|[library_block](library-block.md)|.Idl 파일의 라이브러리 블록 내부 구문을 배치합니다.|
|[ptr](ptr.md)|전체 포인터에 대 한 포인터를 지정합니다.|
|[public](public-cpp-attributes.md)|.Idl 파일 내에서 참조 하지 않는 경우에 typedef 형식 라이브러리로 이동 됩니다 확인 합니다.|
|[ref](ref-cpp.md)|참조 포인터를 식별합니다.|
|[switch_is](switch-is.md)|식 또는 공용 구조체 멤버를 선택 하는 공용 구조체 판별 역할을 하는 식별자를 지정 합니다.|
|[switch_type](switch-type.md)|Union 판별으로 사용 된 변수의 형식을 식별 합니다.|
|[unique](unique-cpp.md)|고유 포인터를 지정합니다.|
|[wire_marshal](wire-marshal.md)|응용 프로그램별 데이터 형식 대신 전송을 위해 사용 될 데이터 형식을 지정 합니다.|

### <a name="enum"></a>enum

|특성|설명|
|---------------|-----------------|
|[custom](custom-cpp.md)|고유한 특성을 정의할 수 있습니다.|
|[export](export.md)|.Idl 파일에 배치할 데이터 구조를 하면 됩니다.|
|[uuid](uuid-cpp-attributes.md)|클래스 또는 인터페이스에 대 한 고유 ID를 지정 합니다.|
|[v1_enum](v1-enum.md)|지정된 된 열거형된 형식 16 비트 기본이 아닌 32 비트 엔터티를 전송할 수 있는지를 전달 합니다.|

### <a name="union"></a>union

|특성|설명|
|---------------|-----------------|
|[custom](custom-cpp.md)|고유한 특성을 정의할 수 있습니다.|
|[export](export.md)|.Idl 파일에 배치할 데이터 구조를 하면 됩니다.|
|[first_is](first-is.md)|전송할 첫 번째 배열 요소의 인덱스를 지정 합니다.|
|[last_is](last-is.md)|전송할 마지막 배열 요소의 인덱스를 지정 합니다.|
|[length_is](length-is.md)|전송할 배열 요소의 수를 지정 합니다.|
|[max_is](max-is.md)|유효한 배열 인덱스에 대 한 최대값을 지정합니다.|
|[size_is](size-is.md)|메모리 크기의 할당 크기의 포인터에 대 한, 큰 크기의 포인터 및 단일 또는 다차원 배열에 대 한 포인터를 지정 합니다.|
|[unique](unique-cpp.md)|고유 포인터를 지정합니다.|
|[uuid](uuid-cpp-attributes.md)|클래스 또는 인터페이스에 대 한 고유 ID를 지정 합니다.|

### <a name="nonencapsulated-union"></a>Nonencapsulated 공용 구조체

|특성|설명|
|---------------|-----------------|
|[ms_union](ms-union.md)|Nonencapsulated 공용 구조체의 네트워크 데이터 표현 맞춤을 제어합니다.|
|[no_injected_text](no-injected-text.md)|컴파일러 특성 사용으로 인해 코드를 삽입 하지 못하도록 방지 합니다.|

### <a name="struct"></a>struct

|특성|설명|
|---------------|-----------------|
|[aggregatable](aggregatable.md)|클래스에서 집계를 지원함을 나타냅니다.|
|[aggregates](aggregates.md)|컨트롤을 대상 클래스 집계 됨을 나타냅니다.|
|[appobject](appobject.md)|전체.exe 응용 프로그램을 사용 하 여 연결 된 문서를 나타내고이 형식 라이브러리에서 coclass의 속성과 함수는 전역적으로 사용할 수 있는 응용 프로그램 개체는 coclass를 식별 합니다.|
|[coclass](coclass.md)|ActiveX 컨트롤을 만듭니다.|
|[com_interface_entry](com-interface-entry-cpp.md)|COM 맵에 인터페이스 항목을 추가 합니다.|
|[control](control.md)|사용자 정의 형식 컨트롤을 지정 합니다.|
|[custom](custom-cpp.md)|고유한 특성을 정의할 수 있습니다.|
|[db_column](db-column.md)|행 집합에 지정된 된 열을 바인딩합니다.|
|[db_command](db-command.md)|OLE DB 명령을 만듭니다.|
|[db_param](db-param.md)|입력 또는 출력 매개 변수를 사용 하 여 지정 된 멤버 변수를 연결 하 고 변수를 구분 합니다.|
|[db_source](db-source.md)|데이터 원본에 연결을 만듭니다.|
|[db_table](db-table.md)|OLE DB 테이블을 엽니다.|
|[default](default-cpp.md)|coclass 내에 정의된 custom 또는 dispinterface가 기본 프로그래밍 인터페이스를 나타낸다는 것을 의미합니다.|
|[defaultvtable](defaultvtable.md)|컨트롤에 대 한 기본 vtable 인터페이스와 인터페이스를 정의합니다.|
|[event_receiver](event-receiver.md)|이벤트 수신기를 만듭니다.|
|[event_source](event-source.md)|이벤트 소스를 만듭니다.|
|[export](export.md)|.Idl 파일에 배치할 데이터 구조를 하면 됩니다.|
|[first_is](first-is.md)|전송할 첫 번째 배열 요소의 인덱스를 지정 합니다.|
|[hidden](hidden.md)|항목이 있지만 하지 사용자 기반 브라우저에 표시할지를 나타냅니다.|
|[implements_category](implements-category.md)|클래스에 대해 구현 된 구성 요소 범주를 지정합니다.|
|[last_is](last-is.md)|전송할 마지막 배열 요소의 인덱스를 지정 합니다.|
|[length_is](length-is.md)|전송할 배열 요소의 수를 지정 합니다.|
|[max_is](max-is.md)|유효한 배열 인덱스에 대 한 최대값을 지정합니다.|
|[requires_category](requires-category.md)|대상 클래스의 필수 구성 요소 범주를 지정합니다.|
|[size_is](size-is.md)|메모리 크기의 할당 크기의 포인터에 대 한, 큰 크기의 포인터 및 단일 또는 다차원 배열에 대 한 포인터를 지정 합니다.|
|[source](source-cpp.md)|클래스에서 연결 지점에 대 한 COM 개체의 소스 인터페이스를 지정합니다. 속성 또는 메서드, 개체 또는 VARIANT는 이벤트의 소스인 멤버 반환 됨을 나타냅니다.|
|[threading](threading-cpp.md)|COM 개체에 대 한 스레딩 모델을 지정합니다.|
|[unique](unique-cpp.md)|고유 포인터를 지정합니다.|
|[uuid](uuid-cpp-attributes.md)|클래스 또는 인터페이스에 대 한 고유 ID를 지정 합니다.|
|[version](version-cpp.md)|클래스의 여러 버전 중에서 특정 버전을 식별합니다.|
|[vi_progid](vi-progid.md)|ProgID의 버전에 관계 없이 폼을 지정합니다.|

## <a name="see-also"></a>참고자료

[용도별 특성](attributes-by-usage.md)