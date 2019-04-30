---
title: 'ActiveX 컨트롤 컨테이너: ActiveX 컨트롤 포함 수동 설정'
ms.date: 09/12/2018
helpviewer_keywords:
- AfxEnableControlContainer method [MFC]
- ActiveX control containers [MFC], enabling
- ActiveX controls [MFC], enabling containers
ms.assetid: 833bcde9-c9ad-4709-ad12-2fc2150fb6a5
ms.openlocfilehash: 80ca25192f3dbda711b0398917cfa68571cd2c55
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394938"
---
# <a name="activex-control-containers-manually-enabling-activex-control-containment"></a>ActiveX 컨트롤 컨테이너: ActiveX 컨트롤 포함 수동 설정

응용 프로그램을 생성 하는 MFC 응용 프로그램 마법사를 사용 하는 경우 ActiveX 컨트롤 지원이 활성화 되지 않았으므로 사용 하는 경우에 수동으로이 지원을 추가 하려고 합니다. 이 문서에서는 수동으로 ActiveX 컨트롤 포함에 기존 OLE 컨테이너 응용 프로그램을 추가 하는 것에 대 한 프로세스를 설명 합니다. 사전에 OLE 컨테이너에서 ActiveX 컨트롤 지원 한다고 알고 있는 경우 문서를 참조 [MFC ActiveX 컨트롤 컨테이너 만들기](../mfc/reference/creating-an-mfc-activex-control-container.md)합니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용 되지 해야 하는 레거시 기술입니다. ActiveX를 대체 하는 최신 기술에 대 한 자세한 내용은 참조 하세요. [ActiveX 컨트롤](activex-controls.md)합니다.

> [!NOTE]
>  이 문서는 대화 상자 기반 ActiveX 컨트롤 컨테이너 프로젝트 라는 컨테이너와 절차 및 코드의 예로 Circ 라는 포함 된 컨트롤을 사용 합니다.

ActiveX 컨트롤을 지원 하려면 두 프로젝트의 파일에 코드 한 줄을 추가 해야 합니다.

- 기본 대화에 수정 `InitInstance` 함수 (컨테이너에서 찾을 수 있습니다. CPP)를 호출 하는 MFC 응용 프로그램 마법사로 [AfxEnableControlContainer](reference/ole-initialization.md#afxenablecontrolcontainer)다음 예제와 같이:

   [!code-cpp[NVC_MFCOleContainer#34](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_1.cpp)]
    [!code-cpp[NVC_MFCOleContainer#35](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_2.cpp)]

- 프로젝트의 STDAFX에 다음을 추가 합니다. H 헤더 파일:

   [!code-cpp[NVC_MFCOleContainer#36](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_3.h)]

다음이 단계를 완료 한 후 클릭 하 여 프로젝트를 다시 빌드합니다 **빌드할** 에 **빌드** 메뉴.

## <a name="see-also"></a>참고자료

[ActiveX 컨트롤 컨테이너](../mfc/activex-control-containers.md)
