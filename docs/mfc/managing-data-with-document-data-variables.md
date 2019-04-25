---
title: 문서 데이터 변수로 데이터 관리
ms.date: 11/04/2016
helpviewer_keywords:
- documents [MFC], data storage
- friend classes [MFC]
- classes [MFC], friend
- data [MFC]
- data [MFC], documents
- collection classes [MFC], used by document object
- document data [MFC]
- member variables [MFC], document class [MFC]
ms.assetid: e70b87f4-8c30-49e5-8986-521c2ff91704
ms.openlocfilehash: dc21bd4b3dbe7609a33af4b4f93f15a3f5c9a64e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62151997"
---
# <a name="managing-data-with-document-data-variables"></a>문서 데이터 변수로 데이터 관리

문서 클래스의 멤버 변수로 문서의 데이터를 구현 합니다. Scribble 프로그램 형식의 데이터 멤버를 선언 하는 예를 들어 `CObList` -에 대 한 포인터를 저장 하는 연결 된 목록 `CObject` 개체입니다. 이 목록은 자유 선 그리기를 구성 하는 점의 배열을 저장에 사용 됩니다.

문서의 멤버 데이터를 구현 하는 방법을 응용 프로그램의 특성에 따라 달라 집니다. MFC를 out 수 있도록 "컬렉션 클래스"의 그룹을 제공, 배열, 목록 및 맵 (사전)를 기반으로 컬렉션을 포함 하 여 C++ 템플릿-와 같은 다양 한 일반적인 데이터 형식 캡슐화 하는 클래스와 함께 `CString`, `CRect`, `CPoint`하십시오 `CSize`, 및 `CTime`합니다. 이러한 클래스에 대 한 자세한 내용은 참조는 [클래스 라이브러리 개요](../mfc/class-library-overview.md) 에 *MFC 참조*합니다.

문서의 멤버 데이터를 정의 하는 경우에 설정 및 데이터 항목을 가져와 다른 유용한 작업을 수행 하려면 문서 클래스에 일반적으로 멤버 함수를 추가 합니다.

보기를 만들 때 뷰에서 설치 문서에 대 한 보기의 포인터를 사용 하 여 문서 개체에 액세스 합니다. 이 보기의 멤버 함수이 포인터를 호출 하 여 검색할 수 있습니다 합니다 `CView` 멤버 함수 `GetDocument`합니다. 이 포인터 고유한 문서 형식으로 캐스팅 해야 합니다. 공용 문서 멤버 포인터를 통해 액세스할 수 있습니다.

Friend 클래스 보기를 확인 하려는 자주 데이터를 전송 하려면 직접 액세스 또는 문서 클래스의 public이 아닌 멤버를 사용 하려는 경우 (에서 C++ 용어) 문서 클래스입니다.

## <a name="see-also"></a>참고자료

[문서 사용](../mfc/using-documents.md)
