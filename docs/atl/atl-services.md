---
title: ATL 서비스
ms.date: 11/04/2016
helpviewer_keywords:
- CServiceModule class
- COM objects, ATL
- services, ATL
- ATL services
ms.assetid: 8c09d1a8-7548-4d2c-947c-9d795a81659b
ms.openlocfilehash: 052169154a62cbd07a82f08087fc2c2db8ae46c5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62251917"
---
# <a name="atl-services"></a>ATL 서비스

ATL COM 개체를 만들려면 서비스에서 실행 되도록 간단히 ATL 프로젝트 마법사에서 서버 옵션 목록에서 서비스 (EXE)을 선택 합니다. 마법사는 파생 클래스를 만든 다음 `CAtlServiceModuleT` 서비스를 구현 합니다.

ATL COM 개체를 서비스로 작성 되 면 로컬 서버로 등록만 됩니다 및 제어판의 서비스 목록에 표시 되지 않습니다. 즉, 서비스 보다는 로컬 서버와 서비스를 디버깅 하는 것이 쉽습니다. 이 서비스로 설치 하려면 명령 프롬프트에서 다음을 실행 합니다.

`YourEXE` `.exe /Service`

파일을 제거 하려면 다음을 실행 합니다.

`YourEXE` `.exe /UnregServer`

이 섹션의 처음 4 개 항목에서는 실행 하는 동안 발생 하는 작업을 설명 `CAtlServiceModuleT` 멤버 함수입니다. 이러한 항목 이라고 하는 함수는 일반적으로 동일한 순서로 나타납니다. 이러한 항목에 대 한 이해를 향상을 위해 참조로 ATL 프로젝트 마법사에서 생성 한 소스 코드를 사용 하는 것이 좋습니다. 이러한 처음 4 개 항목은:

- [Catlservicemodulet:: Start 함수](../atl/reference/catlservicemodulet-class.md#start)

- [Catlservicemodulet:: Servicemain 함수](../atl/reference/catlservicemodulet-class.md#servicemain)

- [Catlservicemodulet:: Run 함수](../atl/reference/catlservicemodulet-class.md#run)

- [Catlservicemodulet:: Handler 함수](../atl/reference/catlservicemodulet-class.md#handler)

마지막 세 항목은 서비스 개발에 관련 된 개념을 설명 합니다.

- [레지스트리 항목](../atl/registry-entries.md) ATL 서비스

- [DCOMCNFG](../atl/dcomcnfg.md)

- [디버깅 팁](../atl/debugging-tips.md) ATL 서비스

## <a name="see-also"></a>참고자료

[개념](../atl/active-template-library-atl-concepts.md)
