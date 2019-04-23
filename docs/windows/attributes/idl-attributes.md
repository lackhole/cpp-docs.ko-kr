---
title: IDL 특성 (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- attributes [C++/CLI], reference topics
- IDL attributes
- .idl files [C++], attributes
- IDL files [C++], attributes
- .idl files [C++]
ms.assetid: 04c596f4-c97b-4952-8053-316678b1d0b6
ms.openlocfilehash: a699e327eec056bbb36747840990bb9c7ccc259b
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59039511"
---
# <a name="idl-attributes"></a>IDL 특성

일반적으로.idl 파일을 유지 관리에 사용 했던 것:

- 구조를 수정할 수 있게 되기를.idl 파일의 구문에 익숙해야 합니다.

- .Idl 파일의 여러 측면을 수정할 수 있는 마법사를 사용 합니다.

이제 시각적 개체를 사용 하 여 소스 코드 파일 내에서.idl 파일을 수정할 수 있습니다 C++ IDL 특성입니다. 대부분의 경우 시각적 개체에서 C++ IDL 특성 이름이 같은 MIDL 특성으로 합니다. 때 시각적 개체의 이름을 C++ IDL 특성 및 특성을 MIDL 같으면, 즉, 해당 시각적 개체 배치 C++ 소스 코드 파일에서 특성 마다 MIDL 특성을 포함 하는.idl 파일에서 발생 합니다. 그러나 시각적 개체 C++ IDL 특성을 MIDL 특성의 모든 기능을 제공 하지 않을 수 있습니다.

사용 하 여 사용 하지 않는 경우 [COM 특성](com-attributes.md), IDL 특성 인터페이스를 정의할 수 있습니다. 소스 코드를 컴파일할 때 생성 된.idl 파일을 정의 하는 특성이 사용 됩니다. ATL 프로젝트에서 COM 특성을 사용 하는 경우 일부 IDL 특성을 같은 `coclass`, 코드를 프로젝트에 삽입 합니다.

사실은 [idl_quote](idl-quote.md) 시각적 개체의 현재 버전에서 지원 되지 않는 MIDL 구문을 사용할 수 있습니다 C++합니다. 이 기타 특성과 같은 [importlib](importlib.md) 하 고 [includelib](includelib-cpp.md) 현재 시각적 개체에서 기존.idl 파일을 사용 하는 데 도움이 C++ 프로젝트입니다.

|특성|설명|
|---------------|-----------------|
|[aggregatable](aggregatable.md)|컨트롤을 다른 컨트롤에서 집계할 수 있는지를 나타냅니다.|
|[appobject](appobject.md)|전체 EXE 응용 프로그램과 연결 된 문서를 나타내고이 형식 라이브러리에서 coclass의 속성과 함수는 전역적으로 사용할 수 있는 응용 프로그램 개체는 coclass를 식별 합니다.|
|[async_uuid](async-uuid.md)|MIDL 컴파일러에 지시 합니다 COM 인터페이스의 동기 및 비동기 버전을 정의 하는 UUID를 지정 합니다.|
|[bindable](bindable.md)|속성이 데이터 바인딩을 지원합니다.|
|[call_as](call-as.md)|사용 불가능 한 함수를 원격 함수에 매핑할 수 있습니다.|
|[case](case-cpp.md)|사용 된 [switch_type](switch-type.md) 공용 구조체의 특성입니다.|
|[coclass](coclass.md)|위치 클래스 coclass는.idl 파일에 정의 합니다.|
|[control](control.md)|사용자 정의 형식 컨트롤을 지정 합니다.|
|[cpp_quote](cpp-quote.md)|생성된 된 헤더 파일의 따옴표 없이 지정된 된 문자열을 내보냅니다.|
|[defaultbind](defaultbind.md)|개체를 가장 잘 나타내는 단일, 바인딩 가능한 속성을 나타냅니다.|
|[defaultcollelem](defaultcollelem.md)|Visual Basic 코드 최적화를 위해 사용 합니다.|
|[defaultvalue](defaultvalue.md)|형식화 된 선택적 매개 변수 기본값을 지정할 수 있습니다.|
|[default](default-cpp.md)|coclass 내에 정의된 custom 또는 dispinterface가 기본 프로그래밍 인터페이스를 나타낸다는 것을 의미합니다.|
|[defaultvtable](defaultvtable.md)|컨트롤에 대 한 기본 vtable 인터페이스와 인터페이스를 정의합니다.|
|[dispinterface](dispinterface.md)|.Idl 파일의 인터페이스를 디스패치 인터페이스로 배치합니다.|
|[displaybind](displaybind.md)|바인딩 가능한 사용자에 게 표시 하는 속성을 나타냅니다.|
|[dual](dual.md)|.Idl 파일에 이중 인터페이스와 인터페이스를 배치합니다.|
|[entry](entry.md)|DLL의 진입점을 식별 하 여 모듈에는 내보낸된 함수 또는 상수를 지정 합니다.|
|[first_is](first-is.md)|전송할 첫 번째 배열 요소의 인덱스를 지정 합니다.|
|[helpcontext](helpcontext.md)|도움말 파일에서이 요소에 대 한 정보를 볼 수 있는 컨텍스트 ID를 지정 합니다.|
|[helpfile](helpfile.md)|형식 라이브러리에 대 한 도움말 파일의 이름을 설정합니다.|
|[helpstringcontext](helpstringcontext.md)|.hlp 또는.chm 파일에서 도움말 항목의 ID를 지정합니다.|
|[helpstringdll](helpstringdll.md)|문서 문자열 조회 (지역화)를 수행 하는 데 DLL의 이름을 지정 합니다.|
|[helpstring](helpstring.md)|적용되는 요소를 설명하는 데 사용되는 문자열을 지정합니다.|
|[hidden](hidden.md)|항목이 있지만 하지 사용자 기반 브라우저에 표시할지를 나타냅니다.|
|[idl_module](idl-module.md)|DLL에 진입점을 지정합니다.|
|[idl_quote](idl-quote.md)|특성을 사용할 수 있습니다 또는 IDL을 생성하는 현재 버전의 Visual C++에서 지원되지 않습니다.|
|[ID](id.md)|멤버 함수 (속성 또는 메서드를 인터페이스나 dispinterface)에 대 한 DISPID를 지정합니다.|
|[iid_is](iid-is.md)|인터페이스 포인터에서 가리키는 COM 인터페이스의 IID를 지정 합니다.|
|[immediatebind](immediatebind.md)|데이터베이스는 즉시 알림을 받을 수는 데이터 바인딩된 개체의 속성에는 모든 변경 내용을 나타냅니다.|
|[importlib](importlib.md)|다른 형식 라이브러리에 이미 컴파일된 형식을 만들고 있는 형식 라이브러리에서 사용할 수 있도록 합니다.|
|[import](import.md)|주.idl 파일에서 참조 하려는 정의 포함 하는 다른.idl,.odl, 또는 헤더 파일을 지정 합니다.|
|[include](include-cpp.md)|생성된 된.idl 파일에 포함할 하나 이상의 헤더 파일을 지정 합니다.|
|[includelib](includelib-cpp.md)|생성된 된.idl 파일에 포함 될.idl 또는.h 파일을 사용 하면 됩니다.|
|[in](in-cpp.md)|매개 변수가 호출된 된 프로시저를 호출 하는 프로시저에서 전달할 임을 나타냅니다.|
|[last_is](last-is.md)|전송할 마지막 배열 요소의 인덱스를 지정 합니다.|
|[lcid](lcid.md)|함수는 로캘 식별자를 전달할 수 있습니다.|
|[length_is](length-is.md)|전송할 배열 요소의 수를 지정 합니다.|
|[licensed](licensed.md)|적용 되는 coclass 사용이 허가 되을 사용 하 여 인스턴스화해야 나타냅니다 `IClassFactory2`합니다.|
|[local](local-cpp.md)|MIDL 컴파일러 인터페이스 헤더에 사용 되는 경우에 헤더 생성기로 사용할 수 있습니다. 개별 함수를 사용할 경우 없는 스텁 생성 되는 로컬 프로시저를 지정 합니다.|
|[max_is](max-is.md)|유효한 배열 인덱스에 대 한 최대값을 지정합니다.|
|[module](module-cpp.md)|.Idl 파일의 라이브러리 블록을 정의합니다.|
|[ms_union](ms-union.md)|Nonencapsulated 공용 구조체의 네트워크 데이터 표현 맞춤을 제어합니다.|
|[no_injected_text](no-injected-text.md)|컴파일러 특성 사용으로 인해 코드를 삽입 하지 못하도록 방지 합니다.|
|[nonbrowsable](nonbrowsable.md)|인터페이스 멤버를 속성 브라우저에 표시 되지 해야 나타냅니다.|
|[noncreatable](noncreatable.md)|자체적으로 인스턴스화할 수 없는 개체를 정의 합니다.|
|[nonextensible](nonextensible.md)|지정 된 `IDispatch` 구현 속성만 포함 하 고 메서드 인터페이스 설명에 나열 된 런타임 시 추가 멤버를 사용 하 여 확장할 수 없습니다.|
|[object](object-cpp.md)|사용자 지정 인터페이스를; 식별 사용자 지정 특성을 사용 하 여 동의어입니다.|
|[odl](odl.md)|개체 설명 언어 (ODL) 인터페이스는 인터페이스를 식별합니다.|
|[oleautomation](oleautomation.md)|Automation 호환 인터페이스를 나타냅니다.|
|[optional](optional-cpp.md)|멤버 함수에 대 한 선택적 매개 변수를 지정합니다.|
|[out](out-cpp.md)|호출된 프로시저에서 호출하는 프로시저로 반환된(서버에서 클라이언트로 반환된) 포인터 매개 변수를 식별합니다.|
|[pointer_default](pointer-default.md)|매개 변수 목록에 표시 되는 최상위 포인터를 제외 하 고 모든 포인터에 대 한 기본 포인터 특성을 지정 합니다.|
|[pragma](pragma.md)|생성된 된.idl 파일의 따옴표 없이 지정된 된 문자열을 내보냅니다.|
|[progid](progid.md)|COM 개체의 ProgID를 지정합니다.|
|[propget](propget.md)|속성 접근자 (get) 함수를 지정합니다.|
|[propputref](propputref.md)|값 대신 참조를 사용 하는 속성 설정 함수를 지정 합니다.|
|[propput](propput.md)|속성 설정 함수를 지정합니다.|
|[ptr](ptr.md)|전체 포인터에 대 한 포인터를 지정합니다.|
|[public](public-cpp-attributes.md)|.Idl 파일 내에서 참조 하지 않는 경우에 typedef 형식 라이브러리로 이동 됩니다 확인 합니다.|
|[range](range-cpp.md)|인수 값은 런타임에 설정 된 필드에 허용 되는 값의 범위를 지정 합니다.|
|[readonly](readonly-cpp.md)|변수에 할당을 금지합니다.|
|[ref](ref-cpp.md)|참조 포인터를 식별합니다.|
|[requestedit](requestedit.md)|속성이 `OnRequestEdit` 알림을 지원함을 나타냅니다.|
|[restricted](restricted.md)|라이브러리 또는 모듈, 인터페이스 또는 dispinterface의 멤버를 임의로 호출할 수 없습니다 지정 합니다.|
|[retval](retval.md)|멤버의 반환 값을 받는 매개 변수를 지정 합니다.|
|[size_is](size-is.md)|메모리 크기의 할당 크기의 포인터에 대 한, 큰 크기의 포인터 및 단일 또는 다차원 배열에 대 한 포인터를 지정 합니다.|
|[source](source-cpp.md)|클래스, 속성 또는 메서드 멤버 이벤트의 소스 임을 나타냅니다.|
|[string](string-cpp.md)|나타내는 1 차원 **char**를 **wchar_t**, `byte`, 또는 해당 하는 배열 또는 이러한 배열에 대 한 포인터를 문자열로 간주 해야 합니다.|
|[switch_is](switch-is.md)|식 또는 공용 구조체 멤버를 선택 하는 공용 구조체 판별 역할을 하는 식별자를 지정 합니다.|
|[switch_type](switch-type.md)|Union 판별으로 사용 된 변수의 형식을 식별 합니다.|
|[transmit_as](transmit-as.md)|표시 형식에는 클라이언트 및 서버 응용 프로그램에서 조작, 전송된 형식을 사용 하 여 연결할 컴파일러에 지시 합니다.|
|[uidefault](uidefault.md)|형식 정보 멤버 사용자 인터페이스에 표시 하기 위한 기본 멤버 임을 나타냅니다.|
|[unique](unique-cpp.md)|고유 포인터를 지정합니다.|
|[usesgetlasterror](usesgetlasterror.md)|해당 함수를 호출할 때 오류가 발생 하는, 호출자가 호출할 수 있습니다 호출자에 게 지시 `GetLastError` 오류 코드를 검색 하려면.|
|[uuid](uuid-cpp-attributes.md)|클래스 또는 인터페이스에 대 한 고유 ID를 지정 합니다.|
|[v1_enum](v1-enum.md)|지정된 된 열거형된 형식 16 비트 기본이 아닌 32 비트 엔터티를 전송할 수 있는지를 전달 합니다.|
|[vararg](vararg.md)|함수 인수의 변수 번호를 지정 합니다.|
|[vi_progid](vi-progid.md)|ProgID의 버전에 관계 없이 폼을 지정합니다.|
|[wire_marshal](wire-marshal.md)|응용 프로그램별 데이터 형식 대신 전송을 위해 사용 될 데이터 형식을 지정 합니다.|

## <a name="see-also"></a>참고자료

[그룹별 특성](attributes-by-group.md)
