---
title: MFC ActiveX 컨트롤 컨테이너 만들기
ms.date: 09/12/2018
f1_keywords:
- vc.appwiz.activex.container
helpviewer_keywords:
- MFC ActiveX controls [MFC], containers
- ActiveX control containers [MFC], creating
- containers [MFC], creating
- OLE controls [MFC], containers
ms.assetid: ec70e137-7c14-4940-bd0e-fd4edcc63ea5
ms.openlocfilehash: 7591b3ed84c1703a201e4e62f699df877de36058
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220193"
---
# <a name="creating-an-mfc-activex-control-container"></a>MFC ActiveX 컨트롤 컨테이너 만들기

ActiveX 컨트롤 컨테이너는 실행 (이전의 OLE) ActiveX 컨트롤을 위한 환경을 제공 하는 부모 프로그램입니다. 없는 MFC ActiveX 컨트롤을 포함할 수 있는 응용 프로그램을 만들 수 있지만 MFC를 사용 하 여 작업을 수행 하는 것이 쉽습니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용 되지 해야 하는 레거시 기술입니다. ActiveX를 대체 하는 최신 기술에 대 한 자세한 내용은 참조 하세요. [ActiveX 컨트롤](../activex-controls.md)합니다.

MFC 프로그램 사용 하 여 컨테이너를 만드는 합니다 [MFC 응용 프로그램 마법사](../../mfc/reference/mfc-application-wizard.md) MFC 및 ActiveX 클래스에서 구현 되는 ActiveX 컨트롤 및 자동화의 많은 기능에 액세스할 수 있습니다. 이러한 기능 비주얼 편집, 자동화, 복합 파일 만들기, 포함 및 컨트롤에 대 한 지원. MFC 응용 프로그램 마법사 시각적 편집 옵션을 부모 프로그램에서 지원 되는 컨테이너, 미니 서버, 풀 서버 및 컨테이너와 서버는 프로그램 만들기를 포함 합니다.

- **새 MFC 응용 프로그램**합니다. 자동화를 포함 하는 새 MFC 프로그램을 만들려면 비주얼 편집 복합 파일 또는 지원을 제어, MFC 응용 프로그램 마법사를 사용 하 여 및 적절 한 자동화 옵션을 선택 합니다.

- **기존 MFC 응용 프로그램**합니다. 기존 MFC 응용 프로그램 컨트롤 포함을 추가 하는 경우 참조 [OLE 컨트롤 컨테이너: OLE 컨트롤 포함 수동 설정](../../mfc/activex-control-containers-manually-enabling-activex-control-containment.md)합니다.

### <a name="to-create-an-activex-container-for-any-of-the-following-types-of-applications"></a>다음 유형의 응용 프로그램에 대 한 ActiveX 컨테이너를 만들려면

1. [컨테이너](../../mfc/containers.md)

1. [비주얼 편집](../../mfc/ole-mfc.md)

1. [MFC ActiveX 컨트롤](../../mfc/mfc-activex-controls.md)

## <a name="see-also"></a>참고자료

[C++Visual Studio에서 프로젝트 형식](../../build/reference/visual-cpp-project-types.md)

