---
title: '메뉴 및 리소스: 컨테이너 추가'
ms.date: 11/04/2016
f1_keywords:
- IDP_OLE_INIT_FAILED
- IDP_FAILED_TO_CREATE
- VK_ESCAPE
helpviewer_keywords:
- application accelerator table [MFC]
- VK_ESCAPE key [MFC]
- IDP_FAILED_TO_CREATE macro [MFC]
- visual editing, application menus and resources
- OLE containers [MFC], menus and resources
- accelerator tables [MFC], container applications
- IDP_OLE_INIT_FAILED macro [MFC]
- CONTAIN tutorial [MFC]
- Links menu item [MFC]
ms.assetid: 425448be-8ca0-412e-909a-a3a9ce845288
ms.openlocfilehash: b1a74fef743592d3d052226dac926fc7ddc58578
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62363468"
---
# <a name="menus-and-resources-container-additions"></a>메뉴 및 리소스: 컨테이너 추가

이 문서에서는 메뉴 및 비주얼 편집 컨테이너 응용 프로그램의 다른 리소스에 대 한 필요한 변경에 설명 합니다.

컨테이너 응용 프로그램에서 두 가지 유형의 변경 해야 합니다: OLE 비주얼 편집 및 내부 활성화에 사용 되는 새 리소스의 추가 지원 하도록 기존 리소스를 수정 합니다. 응용 프로그램 마법사를 사용 하 여 컨테이너 응용 프로그램을 만드는 경우 다음이 단계를 수행할 수는 있지만 일부 사용자 지정이 필요할 수 있습니다.

응용 프로그램 마법사를 사용 하지 않는 경우에 OCLIENT 확인 하는 것이 좋습니다. RC에 이러한 변경 내용을 구현 하는 방법을 확인할 OCLIENT 샘플 응용 프로그램에 대 한 리소스 스크립트입니다. MFC OLE 샘플을 참조 하세요 [OCLIENT](../overview/visual-cpp-samples.md)합니다.

이 문서에서 다루는 항목은 다음과 같습니다.

- [컨테이너 메뉴 추가](#_core_container_menu_additions)

- [액셀러레이터 키 테이블 추가](#_core_container_application_accelerator_table_additions)

- [문자열 테이블 추가](#_core_string_table_additions_for_container_applications)

##  <a name="_core_container_menu_additions"></a> 컨테이너 메뉴 추가

편집 메뉴에 다음 항목을 추가 해야 합니다.

|항목|용도|
|----------|-------------|
|**새 개체를 삽입 합니다.**|문서에 연결 되거나 포함 된 항목을 삽입 하려면 OLE 개체 삽입 대화 상자를 엽니다.|
|**연결 하 여 붙여넣기**|문서에 항목에 대 한 링크를 클립보드에 붙여 넣습니다.|
|**OLE 동사**|선택한 항목의 기본 동사를 호출합니다. 텍스트 선택된 된 항목의 기본 동사를 반영 하도록이 메뉴 항목 변경 내용입니다.|
|**링크**|기존 연결 된 항목을 변경 하려면 OLE 링크 편집 대화 상자를 엽니다.|

이 문서에 나열 된 변경 내용을 외에도 소스 파일 AFXOLECL 포함 해야 합니다. RC는 Microsoft Foundation Class 라이브러리 구현에 필요 합니다. 새 개체 삽입만 필요한 메뉴 추가 하는 것입니다. 다른 항목을 추가할 수 있습니다, 되지만 여기에 나열 된 가장 일반적입니다.

포함 된 항목의 내부 활성화를 지원 하려는 경우 컨테이너 응용 프로그램에 대 한 새 메뉴를 만들어야 합니다. 이 메뉴 같은 파일 메뉴 및 이들 사이 배치 하는 두 개의 구분 기호에 있지만 파일을 열 때 사용 되는 팝업 메뉴를 창으로 구성 됩니다. 이러한 구분 기호 서버 (구성 요소) 항목 (응용 프로그램)는 내부에서 활성화 하는 경우 해당 메뉴를 배치 하는 위치를 나타내는 데 사용 됩니다. 이 메뉴 병합 하는 방법에 대 한 자세한 내용은 참조 하세요. [메뉴 및 리소스: 메뉴 병합](../mfc/menus-and-resources-menu-merging.md)입니다.

##  <a name="_core_container_application_accelerator_table_additions"></a> 컨테이너 응용 프로그램에 액셀러레이터 키 테이블 추가

약간 변경 하는 컨테이너 응용 프로그램의 액셀러레이터 키 테이블 리소스는 내부 활성화를 지 원하는 경우 필요 합니다. 첫 번째 변경에는 사용자를를 (ESC) 전체 편집 모드를 취소 하려면 esc 키를 누를 수 있습니다. 기본 액셀러레이터 키 테이블에 다음 항목을 추가 합니다.

|ID|Key|형식|
|--------|---------|----------|
|ID_CANCEL_EDIT_CNTR|VK_ESCAPE|**VIRTKEY**|

두 번째 변경은 내부 활성화에 대해 만든 새 메뉴 리소스에 해당 하는 새 액셀러레이터 키 테이블을 만드는 것입니다. 이 테이블에는 위의 VK_ESCAPE 항목 외에도 파일 및 창 메뉴에 대 한 항목입니다. 다음 예제는 MFC 샘플에서 내부 활성화에 대 한 생성 된 액셀러레이터 키 테이블 [컨테이너](../overview/visual-cpp-samples.md):

|ID|Key|형식|
|--------|---------|----------|
|ID_FILE_NEW|Ctrl+N|**VIRTKEY**|
|ID_FILE_OPEN|Ctrl+O|**VIRTKEY**|
|ID_FILE_SAVE|Ctrl+S|**VIRTKEY**|
|ID_FILE_PRINT|Ctrl+P|**VIRTKEY**|
|ID_NEXT_PANE|VK_F6|**VIRTKEY**|
|ID_PREV_PANE|SHIFT+VK_F6|**VIRTKEY**|
|ID_CANCEL_EDIT_CNTR|VK_ESCAPE|**VIRTKEY**|

##  <a name="_core_string_table_additions_for_container_applications"></a> 컨테이너 응용 프로그램에 대 한 문자열 테이블 추가

에 설명 된 추가 메뉴 항목에 해당 하는 대부분의 컨테이너 응용 프로그램에 대 한 문자열 테이블 변경 [컨테이너 메뉴 추가](#_core_container_menu_additions)합니다. 이러한 각 메뉴 항목 표시 되 면 상태 표시줄에 표시 되는 텍스트를 제공 합니다. 예를 들어 응용 프로그램 마법사 생성 문자열 테이블 항목은 다음과 같습니다.

|ID|문자열|
|--------|------------|
|IDP_OLE_INIT_FAILED|OLE 초기화 하지 못했습니다. OLE 라이브러리 버전이 올바른지 확인 합니다.|
|IDP_FAILED_TO_CREATE|개체를 만들지 못했습니다. 개체가 시스템 레지스트리에 입력 되어 있는지 있는지 확인 합니다.|

## <a name="see-also"></a>참고자료

[메뉴 및 리소스(OLE)](../mfc/menus-and-resources-ole.md)<br/>
[메뉴 및 리소스: 서버 추가](../mfc/menus-and-resources-server-additions.md)
