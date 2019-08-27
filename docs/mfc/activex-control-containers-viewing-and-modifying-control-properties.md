---
title: 'ActiveX 컨트롤 컨테이너: 컨트롤 속성 보기 및 수정'
ms.date: 11/04/2016
helpviewer_keywords:
- properties [MFC], viewing and modifying
- ActiveX control containers [MFC], viewing and modifying properties
- resource editors, viewing and modifying ActiveX controls
- ActiveX controls [MFC], properties
- controls [MFC], properties
ms.assetid: 14ce5152-742b-4e0d-a9ab-c7b456e32918
ms.openlocfilehash: 0a03acfd880bcf63017eec9796315b98e5d5f4d9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394886"
---
# <a name="activex-control-containers-viewing-and-modifying-control-properties"></a>ActiveX 컨트롤 컨테이너: 컨트롤 속성 보기 및 수정

프로젝트에 ActiveX 컨트롤을 삽입할 때는 ActiveX 컨트롤에서 지원되는 속성을 보고 변경하는 것이 유용합니다. 이 문서에서는 이를 수행하기 위해 Visual C++ 리소스 편집기를 사용하는 방법을 설명합니다.

ActiveX 컨트롤 컨테이너 애플리케이션에 포함된 컨트롤이 사용될 경우, 리소스 편집기에서 컨트롤의 속성을 보고 수정할 수 있습니다. 또한 디자인 타임 중에 리소스 편집기를 사용해서 속성 값을 설정할 수도 있습니다. 그런 다음 리소스 편집기는 프로젝트의 리소스 파일에 이러한 값을 자동으로 저장합니다. 그런 다음에는 이 컨트롤의 어떤 인스턴스라도 해당 속성이 이러한 값으로 초기화됩니다.

이 절차에서는 사용자가 컨트롤을 사용자의 프로젝트에 삽입했다고 가정합니다. 내용은 [ActiveX 컨트롤 컨테이너: 컨트롤 컨테이너 응용 프로그램에 컨트롤 삽입](../mfc/inserting-a-control-into-a-control-container-application.md)합니다.

컨트롤의 속성을 확인하는 첫 번째 단계는 프로젝트의 대화 상자 템플릿에 컨트롤 인스턴스를 추가하는 것입니다.

### <a name="to-view-the-properties-of-a-control"></a>컨트롤의 속성을 보려면

1. 리소스 보기에서 엽니다는 **대화 상자** 폴더입니다.

1. 기본 대화 상자 템플릿을 엽니다.

1. 사용 하 여 ActiveX 컨트롤을 삽입 합니다 **ActiveX 컨트롤 삽입** 대화 상자. 자세한 내용은 [보기 및 대화 상자에 ActiveX 컨트롤 추가](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md)합니다.

1. 대화 상자에서 ActiveX 컨트롤을 선택합니다.

1. 속성 창에서 클릭 합니다 **속성** 단추입니다.

사용 된 **속성** 대화 상자를 수정 하 고 즉시 새 속성을 테스트 합니다.

## <a name="see-also"></a>참고자료

[ActiveX 컨트롤 컨테이너](../mfc/activex-control-containers.md)
