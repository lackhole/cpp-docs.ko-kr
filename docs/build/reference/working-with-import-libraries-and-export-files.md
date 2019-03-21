---
title: 가져오기 라이브러리 및 내보내기 파일을 사용한 작업
ms.date: 11/04/2016
helpviewer_keywords:
- LIB [C++], /DEF option
- import libraries
- LIB [C++], import libraries and export files
- export files
- import libraries, creating
ms.assetid: d8175596-9773-4c2f-959d-b05b065a5161
ms.openlocfilehash: 6f6f2d5c48c63ba6d8a8a7f67a98b949b32a8afa
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57810110"
---
# <a name="working-with-import-libraries-and-export-files"></a>가져오기 라이브러리 및 내보내기 파일을 사용한 작업

가져오기 라이브러리 및 내보내기 파일을 만들려면 LIB /DEF 옵션으로 사용할 수 있습니다. LINK 포함 하는 프로그램을 작성 하는 내보내기 파일을 사용 하 여 (일반적으로 동적 연결 라이브러리 (DLL))를 내보내고 가져오기 라이브러리를 사용 하 여 다른 프로그램의 내보내기에 대 한 참조를 확인 합니다.

Note는.dll을 만들기 전에 예비 단계에서 가져오기 라이브러리를 만드는 경우 전달 해야 개체 파일의 동일한 집합.dll을 빌드할 때 가져오기 라이브러리를 빌드할 때는 전달 합니다.

대부분의 경우 가져오기 라이브러리를 만들려면 LIB를 사용할 필요가 없습니다. 내보내기를 포함 하는 프로그램 (실행 파일 또는 DLL)을 연결 하면 링크는 내보내기에 설명 하는 가져오기 라이브러리를 자동으로 만듭니다. 나중에 이러한 내보내기를 참조 하는 프로그램을 연결 하면 가져오기 라이브러리를 지정 합니다.

그러나 DLL로 가져오기도 수행 하는 프로그램을 내보내면 때 여부 직접 또는 간접적으로 사용 해야 LIB 가져오기 라이브러리 중 하나를 만들려면. LIB 가져오기 라이브러리를 만들 때 또한 내보내기 파일을 만듭니다. Dll 중 하나를 연결 하는 경우에 내보내기 파일을 사용 해야 합니다.

## <a name="see-also"></a>참고자료

[LIB 참조](lib-reference.md)
