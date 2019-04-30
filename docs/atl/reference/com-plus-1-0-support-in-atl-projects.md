---
title: COM + 1.0 ATL 프로젝트에서 지원 합니다.
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.ATL.MTS
helpviewer_keywords:
- ATL projects, COM+ 1.0 support
ms.assetid: 51fb08ac-d632-4657-a4e0-d3f989f0b6f8
ms.openlocfilehash: 39a3597b8df833d89942e31b361f791b14ceb8c9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62278477"
---
# <a name="com-10-support-in-atl-projects"></a>COM + 1.0 ATL 프로젝트에서 지원 합니다.

사용할 수는 [ATL 프로젝트 마법사](../../atl/reference/creating-an-atl-project.md) COM + 1.0 구성 요소에 대 한 기본 지원을 사용 하 여 프로젝트를 만들려고 합니다.

COM + 1.0는 분산된 된 구성 요소 기반 응용 프로그램을 개발 하기 위한 설계 되었습니다. 또한 배포 및 이러한 응용 프로그램을 관리 하기 위한 런타임 인프라를 제공 합니다.

선택 하는 경우는 **COM + 1.0 지원** 확인란을 마법사 링크 단계에서 빌드 스크립트를 수정 합니다. 특히, COM + 1.0 프로젝트 링크를 다음 라이브러리:

- comsvcs.lib

- Mtxguid.lib

선택 하는 경우는 **COM + 1.0 지원** 확인란을 선택할 수도 있습니다 **구성 요소 등록자 지원**합니다. 구성 요소 관리자에는 COM + 1.0 개체를 구성 요소 목록을 가져오려면, 구성 요소를 등록 하거나 (개별적으로 또는 한 번에 모두) 구성 요소 등록을 취소할 수 있습니다.

## <a name="see-also"></a>참고자료

[ATL COM 개체 기본 사항](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[ATL 및 C 런타임 코드를 사용한 프로그래밍](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[기본 ATL 프로젝트 구성](../../atl/reference/default-atl-project-configurations.md)
