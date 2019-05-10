---
title: 대체 가능 매개 변수 (ATL 등록자)를 사용 하 여
ms.date: 11/04/2016
helpviewer_keywords:
- '%MODULE%'
ms.assetid: 0b376994-84a6-4967-8d97-8c01dfc94efe
ms.openlocfilehash: 1c772c0493b351d8452400a4fb1e3949ab6f28f2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62274146"
---
# <a name="using-replaceable-parameters-the-registrar39s-preprocessor"></a>대체 가능 매개 변수를 사용 하 여 (등록 기관에&#39;s 전처리기)

대체 가능 매개 변수는 런타임 데이터를 지정 하는 등록자의 클라이언트를 허용 합니다. 이렇게 하려면 등록자에 스크립트에서 대체 가능 매개 변수를 사용 하 여 관련 된 값을 입력 하는 대체 맵을 유지 관리 합니다. 등록 기관은 런타임 시 이러한 항목을 만듭니다.

##  <a name="_atl_using_.25.module.25"></a> 모듈 %를 사용 하 여

합니다 [ATL 컨트롤 마법사](../atl/reference/atl-control-wizard.md) 사용 하는 스크립트를 자동으로 생성 `%MODULE%`합니다. ATL 서버 DLL 또는 EXE의 실제 위치에 대 한이 대체 가능 매개 변수를 사용합니다.

## <a name="concatenating-run-time-data-with-script-data"></a>스크립트 데이터를 사용 하 여 런타임 데이터를 연결합니다.

전처리기를 사용 하는 다른 스크립트 데이터를 사용 하 여 런타임 데이터를 연결 하는 것입니다. 예를 들어, 문자열을 사용 하 여 모듈 전체 경로 포함 하는 항목이 필요한 "`, 1`" 끝에 추가 됩니다. 먼저 다음 확장을 정의 합니다.

```
'MySampleKey' = s '%MODULE%, 1'
```

그런 다음 호출 하기 전에 스크립트 처리에 나열 된 메서드 중 하나 [스크립트 호출](../atl/invoking-scripts.md), 대체 맵에 추가:

[!code-cpp[NVC_ATL_Utilities#113](../atl/codesnippet/cpp/using-replaceable-parameters-the-registrar-s-preprocessor_1.cpp)]

등록 기관은 구문 분석 중 스크립트를 확장 `'%MODULE%, 1'` 에 `c:\mycode\mydll.dll, 1`입니다.

> [!NOTE]
>  등록자 스크립트에서 4k 최대 토큰 크기입니다. (토큰 구문에서 인식할 수 있는 요소입니다.) 이 생성 되거나 전처리기에 의해 확장 된 토큰이 포함 됩니다.

> [!NOTE]
>  런타임 시 대체 값을 대체를 스크립트에서 호출을 제거 합니다 [DECLARE_REGISTRY_RESOURCE](../atl/reference/registry-macros.md#declare_registry_resource) 하거나 [DECLARE_REGISTRY_RESOURCEID](../atl/reference/registry-macros.md#declare_registry_resourceid) 매크로입니다. 대신, 고유한로 바꾸거나 `UpdateRegistry` 메서드를 호출 하는 [CAtlModule::UpdateRegistryFromResourceD](../atl/reference/catlmodule-class.md#updateregistryfromresourced) 또는 [CAtlModule::UpdateRegistryFromResourceS](../atl/reference/catlmodule-class.md#updateregistryfromresources), _ATL_REGMAP_ 배열을 전달 합니다. 항목 구조입니다. _ATL_REGMAP_ENTRY 배열을 {NULL, NULL}로 설정 되어 있는 적어도 하나의 항목이 있고이 항목은 항상 마지막 항목 이어야 합니다. 그렇지 않으면 액세스 위반 오류가 됩니다 때 생성 `UpdateRegistryFromResource` 라고 합니다.

> [!NOTE]
>  실행 파일을 출력 하는 프로젝트를 빌드할 때 ATL 경로 이름 사용 하 여 런타임 시 만들어집니다 주위에 따옴표를 자동으로 추가 합니다 **모듈 %** 등록자 스크립트 매개 변수입니다. 경로 이름을 따옴표를 포함 하지 않으려면 사용 하 여 새 **묶지** 매개 변수 대신 합니다.
>
>  DLL을 출력 하는 프로젝트를 빌드할 때 ATL는 추가 하지 인용 부호 된 경로 이름으로 경우 **% 모듈** 하거나 **묶지** 사용 됩니다.

## <a name="see-also"></a>참고자료

[등록자 스크립트 만들기](../atl/creating-registrar-scripts.md)
