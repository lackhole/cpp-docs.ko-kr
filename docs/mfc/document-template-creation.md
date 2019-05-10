---
title: 문서 템플릿 만들기
ms.date: 11/04/2016
helpviewer_keywords:
- document templates [MFC]
- constructors [MFC], document template
- document templates [MFC], creating
- MFC, document templates
- templates [MFC], document templates
ms.assetid: c87f1821-7cbf-442e-9690-f126ae7fb783
ms.openlocfilehash: 85ff6ad47b37d85c812608dbee918f0543730eae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62219810"
---
# <a name="document-template-creation"></a>문서 템플릿 만들기

대 한 응답으로 새 문서를 만들 때를 **새로 만들기** 또는 **열기** 에서 명령을 합니다 **파일** 메뉴 문서 서식 파일 보기를 통해 새 프레임 창도 만듭니다는 문서입니다.

문서 템플릿 생성자는 문서, 창 및 템플릿을 만들 수는 보기의 유형을 지정 합니다. 문서 템플릿 생성자에 전달할 인수에 의해 결정 됩니다. 다음 코드에서는 생성 된 [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md) 샘플 응용 프로그램:

[!code-cpp[NVC_MFCDocView#7](../mfc/codesnippet/cpp/document-template-creation_1.cpp)]

새 포인터 `CMultiDocTemplate` 개체를 인수로 사용 됩니다 [AddDocTemplate](../mfc/reference/cwinapp-class.md#adddoctemplate)합니다. 인수를 `CMultiDocTemplate` 생성자 문서 형식의 메뉴 및 액셀러레이터를 사용 하 여 연결 된 리소스 ID를 포함 하 고 세 가지 사용 합니다 [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class) 매크로 합니다. `RUNTIME_CLASS` 반환 된 [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) 개체에 대 한는 C++ 인수로 라는 클래스. 세 가지 `CRuntimeClass` 문서 템플릿 생성자에 전달 된 개체는 문서 만들기 프로세스 중 지정된 된 클래스의 새 개체를 만드는 데 필요한 정보를 제공 합니다. 이 예제에서는 만든 문서 템플릿 만드는 방법을 보여 줍니다 `CScribDoc` 개체와 함께 `CScribView` 연결 개체입니다. 보기는 표준 MDI 자식 프레임 창으로 묶여 있습니다.

## <a name="see-also"></a>참고자료

[문서 템플릿 및 문서/뷰 만들기 프로세스](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[문서/뷰 만들기](../mfc/document-view-creation.md)<br/>
[MFC 개체 간 관계](../mfc/relationships-among-mfc-objects.md)<br/>
[새 문서, 창 및 뷰 만들기](../mfc/creating-new-documents-windows-and-views.md)
