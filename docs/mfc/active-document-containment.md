---
title: 액티브 문서 포함
ms.date: 11/04/2016
helpviewer_keywords:
- active documents [MFC], containers
- containers [MFC], active document
- MFC, COM support
- active document containers [MFC], about active document containers
- MFC COM, active document containment
ms.assetid: b8dfa74b-75ce-47df-b75e-fc87b7f7d687
ms.openlocfilehash: dc13384454c4732d3efbf99def5d05dd4f2d44aa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394969"
---
# <a name="active-document-containment"></a>액티브 문서 포함

액티브 문서 포함은 작업을 만들고 각 문서 유형에 대 한 여러 응용 프로그램 프레임을 사용 하도록 요구 하는 대신 문서는 단일 프레임을 제공 하는 기술입니다. OLE 콘텐츠의 일부만 활성화 될 수 있는 복합 문서 내에서 포함 된 개체를 사용 하 여 작동 하는 기본 OLE 기술에서 다릅니다. 액티브 문서 포함을 사용 하 여 단일 프레임의 컨텍스트 내에서 전체 문서 (즉, 전체 응용 프로그램에 연결된 메뉴, 도구 모음 및 등을 포함 하 여)를 활성화 합니다.

액티브 문서 포함 기술 바인더를 구현 하는 Microsoft Office에 대 한 원래 개발 되었습니다. 그러나 Office Binder 이외의 액티브 문서 컨테이너를 지원할 수 있을 정도로 유연 기술과 Office 및 Office 호환 응용 프로그램 이외의 문서 서버를 지원할 수 있습니다.

액티브 문서를 호스팅하는 응용 프로그램에서 호출 되는 [액티브 문서 컨테이너](../mfc/active-document-containers.md)합니다. 이러한 컨테이너의 예로 Microsoft Office Binder 또는 Microsoft Internet Explorer를 들 수 있습니다.

액티브 문서 포함 OLE의 복합 문서 기술을 OLE에 대 한 확장 집합을 문서화 하는 대로 구현 됩니다. 확장에는 포함, 전체 개체가 포함 된 콘텐츠는 단일 대신 전체 문서를 나타낼 수 있도록 하는 추가 인터페이스입니다. OLE 문서와 마찬가지로 액티브 문서 포함 액티브 문서 및 액티브 문서 자체에 대 한 사용자 인터페이스 및 조작 기능을 제공 하는 서버에 대 한 표시 공간을 제공 하는 컨테이너를 사용 합니다.

[액티브 문서 서버](../mfc/active-document-servers.md) 는 지 원하는 하나 이상의 활성 문서 클래스 (예: Word, Excel 또는 PowerPoint) 응용 프로그램 자체 각 개체가 개체에서 활성화할 수 있도록 확장 프로그램 인터페이스를 지원 하는 위치는 적합 한 컨테이너입니다.

[액티브 문서](../mfc/active-documents.md) (Word 또는 Excel 같은 액티브 문서 서버에서 제공 됨) 문서가 기본적으로 두는 전면적인, 기존의 다른 액티브 문서 컨테이너 내에서 개체와 포함 된 합니다. 포함 된 개체와 달리 액티브 문서 해당 페이지를 완전히 제어 있고 (사용 하 여 모든 기본 명령 및 도구) 응용 프로그램의 전체 인터페이스를 편집 하려면 사용자에 게 제공 됩니다.

활성 문서에서 표준 OLE 포함된 개체를 구분 하 여 가장 인식 됩니다. OLE 규칙 포함된 된 개체를 소유 하는 문서의 페이지 내에서 표시 되는 하나 이며 문서 OLE 컨테이너에 의해 관리 됩니다. 컨테이너는 문서의 나머지 부분을 사용 하 여 포함된 된 개체의 데이터를 저장합니다. 그러나 포함 된 개체는 제한에 표시 되는 페이지를 제어 하지 않습니다.

액티브 문서 컨테이너 응용 프로그램의 사용자 (Office Binder의 섹션 이라고 함)는 액티브 문서를 만들 수 있습니다 (이러한 응용 프로그램은 사용 하도록 설정 하는 활성 문서) 제공는 원하는 응용 프로그램을 사용 하 여, 아직 사용자로 결과 프로젝트를 관리할 수는 고유 이름을 지정할 수 있는 단일 엔터티를 저장, 인쇄, 등에. 동일한 방법으로 인터넷 브라우저의 사용자가 로컬 파일 시스템 뿐만 아니라 전체 네트워크를 단일 위치에서 해당 저장소에서 문서를 찾아볼 수 있는 단일 문서 저장소 엔터티로 처리할 수 있습니다.

## <a name="sample-programs"></a>샘플 프로그램

- 합니다 [MFCBIND](../overview/visual-cpp-samples.md) 샘플에서는 활성 문서 컨테이너 응용 프로그램의 구현을 보여 줍니다.

## <a name="see-also"></a>참고자료

[MFC COM](../mfc/mfc-com.md)
