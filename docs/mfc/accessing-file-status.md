---
title: 파일 상태 액세스
ms.date: 11/04/2016
helpviewer_keywords:
- files [MFC], status information
- examples [MFC], file status
- files [MFC], accessing
- file status [MFC]
- status of files [MFC]
ms.assetid: 1b8891d6-eb0f-4037-a837-4928fe595222
ms.openlocfilehash: 26c263b2d7e4e0243444925cb9416cb337dcd79d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392962"
---
# <a name="accessing-file-status"></a>파일 상태 액세스

`CFile`은 파일 존재 여부, 생성/수정 날짜 및 시간, 논리적 크기와 경로 등을 비롯한 파일 상태도 가져올 수 있습니다.

### <a name="to-get-file-status"></a>파일 상태를 가져오려면

1. 사용 된 [CFile](../mfc/reference/cfile-class.md) 가져오고 파일에 대 한 정보를 설정 하는 클래스입니다. 유용한 응용 프로그램 하나를 사용 하는 `CFile` 정적 멤버 함수 **GetStatus** 파일이 있는지 확인 합니다. **GetStatus** 지정 된 파일이 없는 경우 0을 반환 합니다.

따라서 결과 사용할 수 있습니다 **GetStatus** 사용할지 여부를 결정 하는 **cfile:: Modecreate** 다음 예제와 같이 파일을 열 때 플래그:

[!code-cpp[NVC_MFCFiles#3](../atl-mfc-shared/reference/codesnippet/cpp/accessing-file-status_1.cpp)]

관련 정보를 참조 하세요 [Serialization](../mfc/serialization-in-mfc.md)합니다.

## <a name="see-also"></a>참고자료

[파일](../mfc/files-in-mfc.md)
