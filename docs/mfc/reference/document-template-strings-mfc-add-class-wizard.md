---
title: MFC 클래스 추가 마법사, 문서 템플릿 문자열
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.mfc.simple.doctemp
helpviewer_keywords:
- MFC Add Class Wizard, document control strings
ms.assetid: 14e1c834-5e79-4dbd-811f-ec8f0a9cdcb2
ms.openlocfilehash: de0b483b6b3d242ee05680c47ae29ed675d54a36
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62322427"
---
# <a name="document-template-strings-mfc-add-class-wizard"></a>MFC 클래스 추가 마법사, 문서 템플릿 문자열

마법사의이 페이지는 다음 조건을 충족 하는 클래스에 대해서만 제공 됩니다.

- MFC 프로젝트의 문서/뷰 아키텍처를 지원합니다.

- 새 클래스의 기본 클래스는 [CFormView](../../mfc/reference/cformview-class.md)합니다.

- 확인란 **DocTemplate 생성 리소스** 확인 합니다 **이름** 부분을 [MFC 클래스 마법사](../../mfc/reference/mfc-add-class-wizard.md)합니다.

마법사 폼 뷰 디자인, 관리 및 지역화에 도움이 되도록 다음 값에 대 한 기본값을 제공 합니다. 대부분의 문서 템플릿 문자열에 표시 되 고 폼의 사용자가 사용 되므로로 지역화 됩니다는 **리소스 언어** 에 표시 된 합니다 [응용 프로그램 종류](../../mfc/reference/application-type-mfc-application-wizard.md) MFC 응용 프로그램 마법사의 페이지 프로젝트를 만든 경우.

> [!NOTE]
>  파생 된 클래스 마법사 자동 인쇄 지원을 제공 하지 않습니다 `CFormView`합니다.

참조 [문서 템플릿 및 문서/뷰 만들기 프로세스](../../mfc/document-templates-and-the-document-view-creation-process.md) 자세한 내용은 합니다.

## <a name="nonlocalized-strings"></a>지역화 되지 않은 문자열

사용자 문서를 작성 하는 응용 프로그램에 적용 됩니다. 사용자 연 문서를 저장할 더 쉽게 문서 형식에 있는 경우 파일 확장명과 파일 유형 id입니다. 이러한 항목은 사용자가 아니라 시스템에서 사용 되므로 하지 지역화 됩니다.

- **파일 확장명**

   이 forms 응용 프로그램에 대 한 문서 형식과 연결 된 파일 확장명을 설정 합니다. 파일 확장 기본 클래스 이름을 기반으로 합니다. 예를 들어 새 MFC 클래스 이름은 `CWidget`, 기본적으로 파일 확장명은. wid. 파일 확장명은 파일 필터에 사용 되 고 **열려** 및 **다른 이름으로 저장** 대화 상자.

   파일 확장명을 변경 하면 변경 내용이 반영 됩니다에 **필터 이름을** 상자입니다.

   > [!NOTE]
   > 기본 파일 확장명을 변경 하는 경우에 마침표를 포함 하지 마십시오.

- **파일 유형 ID**

   시스템 레지스트리에 문서 유형에 대 한 레이블을 설정합니다.

## <a name="localized-strings"></a>지역화 된 문자열

양식과 읽고 문자열을 지역화 된 응용 프로그램의 사용자가 사용 하는 문서와 관련 된 문자열을 생성 합니다.

- **문서 형식 이름**

   응용 프로그램의 문서를 그룹화 할 수 있습니다 하는 문서 유형을 식별 합니다. 기본적으로 클래스의 이름에 따라 됩니다. 예를 들어 새 MFC 클래스 이름은 **CWidget**, 기본적으로 문서 형식 이름은 위젯입니다. 기본값을 변경 해도이 대화 상자에서 다른 옵션은 변경 되지 않습니다.

- **필터 이름**

   사용자 지정 된 파일 형식의 파일을 찾으려면 나타낼 수 있는 이름을 설정 합니다. 이 옵션은에서 사용할 수는 **파일 형식** 및 **형식으로 저장** 에서 표준 Windows 옵션 **열기** 및 **로 저장** 대화 상자. 기본적으로 이름을 기반에 프로젝트 이름으로 plus에 표시 된 파일을 뒤에 확장명이 **파일 확장명**합니다. 예를 들어 프로젝트 이름이 위젯 및 파일 확장명은.wid, 합니다 **필터 이름을** 위젯 파일 (*.wid)는 기본적으로 합니다.

- **파일의 새 약식 이름**

   표준 Windows에 표시 이름을 설정 합니다 **새로 만들기** 대화 상자에서 프로젝트에 둘 이상의 문서 템플릿이 있을 경우. 응용 프로그램을 [자동화 서버](../../mfc/automation-servers.md), 자동화 개체의 짧은 이름으로이 이름이 사용 됩니다. 기본적으로이 이름은 클래스 이름에 기반 합니다.

- **파일 형식의 긴 이름**

   시스템 레지스트리에 파일 형식 이름을 설정합니다. 자동화 서버 응용 프로그램을 사용 하는 경우이 이름은 자동화 개체의 긴 이름으로 사용 됩니다. 기본적으로이 이름은 클래스 이름 및은 기반으로 합니다. 문서입니다. 예를 들어 클래스 이름이 `CWidget`의 **파일 형식 긴 이름** 위젯 문서입니다.

- **문서 클래스**

   프로젝트의 문서 클래스를 나타냅니다. 기본적으로이 클래스는 기본 응용 프로그램의 문서 클래스에 나열 된는 [클래스를 생성 하는 검토](../../mfc/reference/generated-classes-mfc-application-wizard.md) MFC 응용 프로그램 마법사의 페이지입니다. 프로젝트의 다른 문서 클래스를 추가한 경우 목록에서 다른 문서 클래스를 선택할 수 있습니다.

## <a name="see-also"></a>참고자료

[MFC 클래스 추가 마법사](../../mfc/reference/mfc-add-class-wizard.md)<br/>
[MFC 클래스](../../mfc/reference/adding-an-mfc-class.md)<br/>
[클래스 추가](../../ide/adding-a-class-visual-cpp.md)
