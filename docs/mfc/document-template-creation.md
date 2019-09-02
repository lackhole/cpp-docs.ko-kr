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

**파일** 메뉴에서 **새로 만들기** 또는 **열기** 명령에 대한 응답으로 새 문서를 만들 때 문서 서식은 문서를 볼 수 있는 새 프레임 창도 만듭니다.

문서 템플릿 생성자는 템플릿에서 만들 수 있는 문서, 창 및 보기의 유형을 지정합니다. 이것은 문서 템플릿 생성자에 전달되는 인수에 의해 결정됩니다. 다음 코드에서는 샘플 응용 프로그램에서 [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md)를 생성을 보여줍니다.

[!code-cpp[NVC_MFCDocView#7](../mfc/codesnippet/cpp/document-template-creation_1.cpp)]

새 `CMultiDocTemplate` 개체에 대한 포인터는 [AddDocTemplate](../mfc/reference/cwinapp-class.md#adddoctemplate)의 인수로 사용됩니다. `CMultiDocTemplate` 생성자에 대한 인수에는 문서 형식의 메뉴 및 액셀러레이터와 연관된 리소스 ID 및 [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class) 매크로의 세가지 용도가 포함됩니다. `RUNTIME_CLASS`는 인수라는 C++ 클래스의 [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) 개체를 반환합니다. 문서 템플릿 생성자에 전달된 세 가지 `CRuntimeClass` 개체는 문서 만들기 프로세스 중 지정된 클래스의 새 개체를 만드는데 필요한 정보를 제공 합니다. 이 예제에서는 `CScribView` 개체가 첨부된 `CScribDoc` 개체를 생성하는 문서 템플릿을 만드는 방법을 보여줍니다. 뷰는 표준 MDI 자식 프레임 창으로 구성됩니다.

## <a name="see-also"></a>참고자료

[문서 템플릿 및 문서/뷰 만들기 프로세스](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[문서/뷰 만들기](../mfc/document-view-creation.md)<br/>
[MFC 개체 간 관계](../mfc/relationships-among-mfc-objects.md)<br/>
[새 문서, 창 및 뷰 만들기](../mfc/creating-new-documents-windows-and-views.md)
