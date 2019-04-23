---
title: COM 특성
ms.date: 10/03/2018
helpviewer_keywords:
- attributes [C++/CLI], reference topics
- attributes [COM]
- COM, attributes
ms.assetid: 52a5dd70-e8be-4bba-afd6-daf90fe689a0
ms.openlocfilehash: eb87d3861c6b3066cf482108e2ce2243c8196093
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59038931"
---
# <a name="com-attributes"></a>COM 특성

COM 특성(attribute)은 COM 개발 및 .NET Framework 공용 언어 런타임 개발의 다양한 영역을 지원하는 코드를 삽입합니다. 이러한 영역 범위는 사용자 지정 인터페이스 구현 및 기존 인터페이스 지원, 스톡 속성, 메서드 및 이벤트 지원에 이르기까지 다양합니다. 또한 복합 및 ActiveX 컨트롤 구현에 대한 지원 사항도 찾을 수 있습니다.

|특성|설명|
|---------------|-----------------|
|[aggregatable](aggregatable.md)|컨트롤을 다른 컨트롤에서 집계할 수 있는지를 나타냅니다.|
|[aggregates](aggregates.md)|컨트롤을 대상 클래스 집계 됨을 나타냅니다.|
|[coclass](coclass.md)|COM 인터페이스를 구현할 수 있는 COM 개체를 만듭니다.|
|[com_interface_entry](com-interface-entry-cpp.md)|COM 맵에 인터페이스 항목을 추가 합니다.|
|[implements_category](implements-category.md)|클래스에 대해 구현 된 구성 요소 범주를 지정합니다.|
|[progid](progid.md)|컨트롤에 ProgID를 정의합니다.|
|[rdx](rdx.md)|만들거나 레지스트리 키를 수정 합니다.|
|[registration_script](registration-script.md)|지정 된 등록 스크립트를 실행합니다.|
|[requires_category](requires-category.md)|클래스에 대 한 필수 구성 요소 범주를 지정합니다.|
|[support_error_info](support-error-info.md)|대상 개체에 대해 오류 보고를 지원 합니다.|
|[synchronize](synchronize.md)|메서드에 대 한 액세스를 동기화합니다.|
|[threading](threading-cpp.md)|COM 개체에 대 한 스레딩 모델을 지정합니다.|
|[vi_progid](vi-progid.md)|컨트롤에 대 한 버전 독립 ProgID를 정의합니다.|

## <a name="see-also"></a>참고자료

[그룹별 특성](attributes-by-group.md)