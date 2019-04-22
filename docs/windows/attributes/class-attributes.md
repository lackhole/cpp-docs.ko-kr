---
title: 클래스 특성 (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- attributes [C++/CLI], class attributes
ms.assetid: fad04ea1-d8ff-46d4-bb42-2b4500a6ab60
ms.openlocfilehash: d0913d09c51734f5255271c0d06e639810e0cb58
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59025418"
---
# <a name="class-attributes"></a>클래스 특성

다음 특성을 적용 합니다 [클래스](../../cpp/class-cpp.md) C++ 키워드입니다.

|특성|설명|
|---------------|-----------------|
|[aggregatable](aggregatable.md)|클래스에서 집계를 지원함을 나타냅니다.|
|[aggregates](aggregates.md)|컨트롤을 대상 클래스 집계 됨을 나타냅니다.|
|[appobject](appobject.md)|전체.exe 응용 프로그램을 사용 하 여 연결 된 문서를 나타내고이 형식 라이브러리에서 coclass의 속성과 함수는 전역적으로 사용할 수 있는 응용 프로그램 개체는 coclass를 식별 합니다.|
|[case](case-cpp.md)|사용 된 [switch_type](switch-type.md) 공용 구조체의 특성입니다.|
|[coclass](coclass.md)|ActiveX 컨트롤을 만듭니다.|
|[com_interface_entry](com-interface-entry-cpp.md)|COM 맵에 인터페이스 항목을 추가 합니다.|
|[control](control.md)|사용자 정의 형식 컨트롤을 지정 합니다.|
|[custom](custom-cpp.md)|고유한 특성을 정의할 수 있습니다.|
|[db_command](db-command.md)|OLE DB 명령을 만듭니다.|
|[db_param](db-param.md)|입력 또는 출력 매개 변수를 사용 하 여 지정 된 멤버 변수를 연결 하 고 변수를 구분 합니다.|
|[db_source](db-source.md)|데이터 원본에 연결을 만듭니다.|
|[db_table](db-table.md)|OLE DB 테이블을 엽니다.|
|[default](default-cpp.md)|coclass 내에 정의된 custom 또는 dispinterface가 기본 프로그래밍 인터페이스를 나타낸다는 것을 의미합니다.|
|[defaultvtable](defaultvtable.md)|컨트롤에 대 한 기본 vtable 인터페이스와 인터페이스를 정의합니다.|
|[event_receiver](event-receiver.md)|이벤트 수신기를 만듭니다.|
|[event_source](event-source.md)|이벤트 소스를 만듭니다.|
|[helpcontext](helpcontext.md)|이 요소에 대 한 정보를 볼 수 있는 컨텍스트 ID를 지정 합니다 **도움말** 파일입니다.|
|[helpfile](helpfile.md)|형식 라이브러리에 대 한 도움말 파일의 이름을 설정합니다.|
|[helpstringcontext](helpstringcontext.md)|.hlp 또는.chm 파일에서 도움말 항목의 ID를 지정합니다.|
|[helpstring](helpstring.md)|적용되는 요소를 설명하는 데 사용되는 문자열을 지정합니다.|
|[hidden](hidden.md)|항목이 있지만 하지 사용자 기반 브라우저에 표시할지를 나타냅니다.|
|[implements](implements-cpp.md)|IDL coclass의 구성원으로 강제 적용 되는 디스패치 인터페이스를 지정 합니다.|
|[implements_category](implements-category.md)|클래스에 대해 구현 된 구성 요소 범주를 지정합니다.|
|[module](module-cpp.md)|.Idl 파일의 라이브러리 블록을 정의합니다.|
|[noncreatable](noncreatable.md)|자체적으로 인스턴스화할 수 없는 개체를 정의 합니다.|
|[progid](progid.md)|컨트롤에 ProgID를 정의합니다.|
|[registration_script](registration-script.md)|지정 된 등록 스크립트를 실행합니다.|
|[requestedit](requestedit.md)|속성이 `OnRequestEdit` 알림을 지원함을 나타냅니다.|
|[source](source-cpp.md)|클래스에 연결 지점에 대 한 컨트롤의 소스 인터페이스를 지정합니다. 메서드나 속성에는 `source` 특성 멤버 개체를 반환 함을 나타냅니다 또는 `VARIANT` 이벤트의 소스입니다.|
|[support_error_info](support-error-info.md)|대상 개체에 대해 오류 보고를 지원 합니다.|
|[threading](threading-cpp.md)|컨트롤에 대 한 스레딩 모델을 지정합니다.|
|[uuid](uuid-cpp-attributes.md)|클래스 또는 인터페이스에 대 한 고유 ID를 지정 합니다.|
|[version](version-cpp.md)|클래스의 여러 버전 중에서 특정 버전을 식별합니다.|
|[vi_progid](vi-progid.md)|ProgID의 버전에 관계 없이 폼을 지정합니다.|

## <a name="see-also"></a>참고자료

[용도별 특성](attributes-by-usage.md)