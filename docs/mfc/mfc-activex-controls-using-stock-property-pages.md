---
title: 'MFC ActiveX 컨트롤: 스톡 속성 페이지를 사용 하 여'
ms.date: 09/12/2018
f1_keywords:
- CLSID_CPicturePropPage
- CLSID_CColorPropPage
- CLSID_CFontPropPage
helpviewer_keywords:
- picture stock property pages [MFC]
- CLSID_CFontPropPage [MFC]
- color stock property pages [MFC]
- CLSID_CColorPropPage [MFC]
- fonts [MFC], ActiveX controls
- stock properties [MFC], stock property pages
- CLSID_CPicturePropPage [MFC]
- MFC ActiveX controls [MFC], property pages
ms.assetid: 22638d86-ff3e-4124-933e-54b7c2a25968
ms.openlocfilehash: b73a027422cfe9cbf03afece400c1b513cace151
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62239337"
---
# <a name="mfc-activex-controls-using-stock-property-pages"></a>MFC ActiveX 컨트롤: 스톡 속성 페이지를 사용 하 여

이 문서에서는 ActiveX 컨트롤 및 사용 하는 방법에 대해 사용할 수 있는 스톡 속성 페이지를 설명 합니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용 되지 해야 하는 레거시 기술입니다. ActiveX를 대체 하는 최신 기술에 대 한 자세한 내용은 참조 하세요. [ActiveX 컨트롤](activex-controls.md)합니다.

속성 페이지를 사용 하 여 ActiveX 컨트롤에 대 한 자세한 내용은 다음 문서를 참조 하세요.

- [MFC ActiveX 컨트롤: 속성 페이지](../mfc/mfc-activex-controls-property-pages.md)

- [MFC ActiveX 컨트롤: 다른 사용자 지정 속성 페이지 추가](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)

MFC ActiveX 컨트롤 사용에 대 한 세 가지 스톡 속성 페이지를 제공 합니다. `CLSID_CColorPropPage`, `CLSID_CFontPropPage`, 및 `CLSID_CPicturePropPage`합니다. 이러한 페이지는 각각 주식 색, 글꼴 및 그림 속성에 대 한 사용자 인터페이스를 표시 합니다.

이러한 속성 페이지에 컨트롤에 통합 하려면 컨트롤의 속성 페이지 Id 배열을 초기화 하는 코드를 해당 Id를 추가 합니다. 다음 예제에서는이 코드는 컨트롤 구현 파일에 있는 (합니다. CPP) 모든 세 스톡 속성 페이지 및 기본 속성 페이지를 포함 하는 배열 초기화 (라는 `CMyPropPage` 이 예제의):

[!code-cpp[NVC_MFC_AxOpt#21](../mfc/codesnippet/cpp/mfc-activex-controls-using-stock-property-pages_1.cpp)]

BEGIN_PROPPAGEIDS 매크로에서 속성 페이지의 수는 4는 참고 합니다. 이 ActiveX 컨트롤에서 지원 되는 속성 페이지의 수를 나타냅니다.

이러한 수정을 수행한 후 프로젝트를 다시 빌드하십시오. 컨트롤에는 이제 글꼴, 그림 및 색 속성에 대 한 속성 페이지에 있습니다.

> [!NOTE]
>  현재 운영 체제에 MFC DLL (MFCxx.DLL) 제대로 등록 되지 않은 컨트롤 스톡 속성 페이지에 액세스할 수 없는 경우 수 있습니다. 시각적 개체 설치의 결과 일반적으로 C++ 에서 현재 실행 중인 다른 운영 체제입니다.

> [!TIP]
>  스톡 속성 페이지에 표시 되지 않는 경우 (위의 참고 사항 참조)는 DLL에 대 한 전체 경로 이름 사용 하 여 명령줄에서 RegSvr32.exe를 실행 하 여 DLL을 등록 합니다.

## <a name="see-also"></a>참고자료

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX 컨트롤: 스톡 속성 추가](../mfc/mfc-activex-controls-adding-stock-properties.md)
