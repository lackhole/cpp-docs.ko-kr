---
title: 'TN057: 지역화 된 MFC 구성 요소'
ms.date: 06/28/2018
f1_keywords:
- vc.mfc.components
helpviewer_keywords:
- components [MFC], localizing
- TN057
- resources [MFC], localization
- localization [MFC], MFC resources
- localization [MFC], MFC components
- MFC DLLs [MFC], localizing
- DLLs [MFC], localizing MFC
- localization [MFC], resources
ms.assetid: 5376d329-bd45-41bd-97f5-3d895a9a0af5
ms.openlocfilehash: 812c2d29c42b523d7b88b03741dc20f08ee70f44
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399631"
---
# <a name="tn057-localization-of-mfc-components"></a>TN057: 지역화 된 MFC 구성 요소

> [!NOTE]
> 다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

이 이는 디자인 및 응용 프로그램 또는 OLE 제어 하는 경우 구성 요소를 지역화 하려면 사용할 수 있는 절차 또는 MFC를 사용 하는 DLL의 일부를 설명 합니다.

## <a name="overview"></a>개요

실제로 두 가지 문제 해결 하는 경우에 MFC를 사용 하는 구성 요소를 지역화 합니다. 자신의 리소스를 지역화 해야 먼저-문자열, 대화 상자 및 해당 구성 요소와 관련 된 기타 리소스입니다. 또한 MFC를 사용 하 여 작성 하는 대부분의 구성 요소 등 다양 한 MFC에서 정의한 리소스를 사용 합니다. 지역화 된 MFC 리소스를 제공 해야 합니다. 다행 스럽게도 몇 가지 언어는 이미 MFC 자체에서 제공 됩니다.

또한 구성 요소는 대상 환경 (유럽 또는 DBCS 가능 환경)에서 실행 준비가 되어 있어야 합니다. 대부분의 경우 높은 비트 집합과 문자를 올바르게 처리 하 고 더블 바이트 문자를 사용 하 여 문자열 처리 응용 프로그램에 따라 다릅니다. MFC 기능이 경우 기본적으로 이러한 환경은 둘 다에 대 한 설치 시에 연결 하는 다른 리소스를 사용 하 여 모든 플랫폼에서 사용 되는 전세계 단일 바이너리를 가질 수 있도록 합니다.

## <a name="localizing-your-components-resources"></a>구성 요소의 리소스 지역화

응용 프로그램 또는 DLL 지역화 대상 언어를 일치 하는 리소스를 사용 하 여 리소스를 교체 하기만 참여 시켜야 합니다. 고유한 리소스에 대 한이 작업은 비교적 간단 합니다: 리소스 편집기에서 리소스를 편집 하 고 응용 프로그램을 작성 합니다. 코드를 작성 한 경우 제대로 지역화 하려는 텍스트 없거나 문자열 됩니다에 하드 코딩에 C++ 소스 코드-모든 지역화는 단순히 리소스를 수정 하 여 수행할 수 있습니다. 실제로 지역화 된 버전을 모두 제공 포함 되지 않습니다도 원래 코드의 빌드 구성 요소를 구현할 수 있습니다. 이 더 복잡 하지만 그만한 가치가 이며 메커니즘을 MFC 자체에 대 한 선택입니다. 리소스 편집기 EXE 또는 DLL 파일을 로드 하 고 리소스를 직접 편집 하 여 응용 프로그램을 지역화할 수 이기도 합니다. 가능 하기는 하지만 해당 변경 내용 다시 새 버전의 응용 프로그램을 빌드할 때마다 필요 합니다.

이러한 문제를 피하려면 하나의 방법은 라고도 하는 위성 DLL을 별도 DLL에서 모든 리소스를 찾을 것입니다. 이 DLL은 런타임에 동적으로 로드 한 다음 및 리소스 대신 모든 코드를 사용 하 여 주 모듈에서 해당 DLL에서 로드 됩니다. MFC는이 방법을 직접 지원합니다. MYAPP 이라는 응용 프로그램을 고려 합니다. EXE; MYRES 이라는 DLL에 있는 해당 리소스의 모든 보고 필요도 없습니다 수 있습니다. DLL입니다. 응용 프로그램에서 `InitInstance` 해당 DLL을 로드 하 고 mfc 해당 위치에서 리소스를 로드 하려면 다음을 수행 합니다.

```cpp
CMyApp::InitInstance()
{
    // one of the first things in the init code
    HINSTANCE hInst = LoadLibrary("myres.dll");

    if (hInst != NULL)
        AfxSetResourceHandle(hInst);

    // other initialization code would follow
    // ...
}
```

부터 MFC myapp.exe에서 대신 해당 DLL에서 리소스를 로드 합니다. 그러나 모든 리소스를 있어야 해당 DLL; MFC는 지정된 된 리소스 검색 응용 프로그램의 인스턴스를 검색 하지 않습니다. OLE 컨트롤 뿐만 아니라 동일 하 게에 일반 MFC Dll이이 기술에 적용 됩니다. 설치 프로그램 MYRES의 적절 한 버전을 복사 됩니다. 사용자가 원하는 어떤 리소스 로케일에 따라 DLL입니다.

리소스 만들기를 비교적 쉽게 DLL만 합니다. DLL 프로젝트 만들기, 추가 사용자입니다. RC, 파일 및 필요한 리소스를 추가 합니다. 이 기술을 사용 하지 않는 기존 프로젝트에 있는 경우 해당 프로젝트에서 리소스를 복사할 수 있습니다. 리소스 파일을 프로젝트에 추가한 후 준비가 거의 프로젝트를 빌드합니다. 링커를 포함 하는 옵션을 설정 해야 할 유일한 항목은 **/NOENTRY**합니다. 이 링커에 DLL에 진입점이 없는-코드 없이 있으므로 해당 진입점이 없습니다.

> [!NOTE]
> 시각적 개체의 리소스 편집기 C++ 4.0 이상 당 여러 언어를 지원 합니다. RC 파일입니다. 이 수 매우 쉽게 단일 프로젝트에 지역화를 관리할 수 있습니다. 각 언어에 대 한 리소스는 리소스 편집기에서 생성 하는 전처리기 지시문에 의해 제어 됩니다.

## <a name="using-the-provided-mfc-localized-resources"></a>제공 된 MFC를 사용 하 여 지역화 된 리소스

MFC에서 두 가지 작성 하는 모든 MFC 응용 프로그램을 다시 사용: 코드 및 리소스입니다. 즉, MFC에는 다양 한 오류 메시지, 기본 제공 대화 상자 및 MFC 클래스에 의해 사용 되는 다른 리소스에 있습니다. 응용 프로그램을 완전히 지역화 하려면 응용 프로그램의 리소스 뿐만 아니라 MFC에서 직접 제공 되는 리소스를 지역화 해야 합니다. MFC는 다양 한 다른 언어 리소스 파일 자동으로 하므로 대상으로 하는 언어를 사용 하면 MFC는 이미 지원 언어 중 하나인 경우 하면 지역화 된 리소스를 사용 해야 합니다.

이 문서의 작성 시점 현재 MFC 중국어, 독일어, 스페인어, 프랑스어, 이탈리아어, 일본어 및 한국어를 지원합니다. 이러한 지역화 된 버전을 포함 하는 파일이 MFC\INCLUDE\L.* ('L'은 지역화에 대 한) 디렉터리입니다. 독일어 파일이 MFC\INCLUDE\L.DEU, 예를 들어 있습니다. MFC\INCLUDE에 있는 파일 대신 이러한 RC 파일을 사용 하도록 응용 프로그램으로 인해 추가 `/IC:\PROGRAM FILES\MICROSOFT VISUAL STUDIO .NET 2003\VC7\MFC\INCLUDE\L.DEU` RC 명령줄에 (이것은 예로 든 것일 뿐, Visual C을 설치한 디렉터리 뿐만 아니라 선택한 로캘에 대체 해야 합니다. ++).

MFC를 사용 하 여 응용 프로그램에 정적으로 연결 하는 경우 위의 지침에 따라 작동 합니다. 대부분의 응용 프로그램 동적으로 (이기 때문에 응용 프로그램 마법사에서 기본값)에 연결 합니다. 이 시나리오에서 코드는 동적으로 리소스를 되므로-연결 합니다. 결과적으로, 응용 프로그램에서 리소스를 지역화할 수 있습니다 하지만 MFC 구현 리소스 로드 됩니다는 MFC7x.DLL (또는 이후 버전)에서 또는 MFC7xLOC.DLL 존재 하는 경우. 이 두 가지 다른 관점에서 접근할 수 있습니다.

더 복잡 한 접근 방법을 배송 지역화 MFC7xLOC.DLLs 중 하나 (예: MFC7xDEU, 독일어, 스페인어 등 MFC7xESP.DLL) 또는 이후 버전 이며 사용자가 응용 프로그램을 설치 하는 경우 적절 한 MFC7xLOC.DLL 시스템 디렉터리에 설치 합니다. 이 개발자와 최종 사용자 모두에 대 한 매우 복잡 한 수 있으며 따라서 권장 되지 않습니다. 참조 [기술 참고 56](../mfc/tn056-installation-of-localized-mfc-components.md) 이 기술 및 해당 주의 사항에 대 한 자세한 내용은 합니다.

응용 프로그램 또는 DLL 자체 (또는 해당 위성 DLL 하나를 사용 하는 경우)에 지역화 된 MFC 리소스를 포함 하는 간단 하 고 안전한 방법이입니다. 이 MFC7xLOC.DLL를 올바르게 설치 하는 문제를 피할 수 있습니다. 이렇게 하려면 정적 (RC 명령줄 적절 하 게 지역화 된 리소스를 가리키도록 설정) 위에 지정 된 경우 동일한 지침을 제외한도 제거 해야 하는 `/D_AFXDLL` 정의 하는 응용 프로그램 마법사에서 추가 되었습니다. 때 `/D_AFXDLL` 는 AFXRES를 정의 합니다. H (및 다른 MFC RC 파일) 정의 하지 마십시오 실제로 모든 리소스 (때문에 이러한 가져오게 됩니다 MFC Dll에서 대신).

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
