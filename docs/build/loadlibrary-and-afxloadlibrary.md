---
title: LoadLibrary 및 AfxLoadLibrary
ms.date: 05/24/2018
f1_keywords:
- LoadLibrary
helpviewer_keywords:
- DLLs [C++], AfxLoadLibrary
- DLLs [C++], LoadLibrary
- AfxLoadLibrary method
- LoadLibrary method
- explicit linking [C++]
ms.assetid: b4535d19-6243-4146-a31a-a5cca4c7c9e3
ms.openlocfilehash: 96b8c0ce1116dbb08260573f25f941ca54169127
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822420"
---
# <a name="loadlibrary-and-afxloadlibrary"></a>LoadLibrary 및 AfxLoadLibrary

호출 처리 [LoadLibraryExA](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibraryexa) 하거나 [LoadLibraryExW](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibraryexw)(또는 [AfxLoadLibrary](../mfc/reference/application-information-and-management.md#afxloadlibrary)) DLL에 명시적으로 연결 합니다. 함수가 성공 하는 경우 호출 프로세스의 주소 공간에 지정된 된 DLL을 매핑합니다 및 명시적 링크의 다른 함수와 함께 사용할 수 있는 DLL에 대 한 핸들을 반환 합니다.-예를 들어 `GetProcAddress` 고 `FreeLibrary`합니다.

`LoadLibrary` 암시적 링크에 사용 되는 동일한 검색 시퀀스를 사용 하 여 DLL을 찾으려고 시도 합니다. 시스템 DLL을 찾을 수 없거나 진입점 함수가 FALSE를 반환 하는 경우 `LoadLibrary` NULL을 반환 합니다. 경우에 대 한 호출 `LoadLibrary` 호출 하는 프로세스의 주소 공간에 이미 매핑된 DLL 모듈 지정 함수 모듈의 참조 횟수 증가 고 DLL의 핸들을 반환 합니다.

DLL에는 진입점 함수가 있으면 운영 체제를 호출한 스레드 컨텍스트에서 함수를 호출 `LoadLibrary`합니다. DLL은 이미 연결 된 경우 프로세스는 이전 호출으로 인해 진입점 함수가 호출 되지 않습니다 `LoadLibrary` 에 대 한 해당 호출이 포함 된 `FreeLibrary` 함수입니다.

MFC 확장명 Dll을 로드 하는 MFC 응용 프로그램을 사용 하는 권장 `AfxLoadLibrary` 대신 `LoadLibrary`합니다. `AfxLoadLibrary` 호출 하기 전에 스레드 동기화를 처리 `LoadLibrary`합니다. (함수 프로토타입) 인터페이스 `AfxLoadLibrary` 같습니다 `LoadLibrary`합니다.

Windows에서 DLL을 로드할 수 없는 경우 프로세스 오류 로부터 복구를 시도할 수 있습니다. 예를 들어 프로세스 오류의 사용자에 게 알림 및 DLL에 다른 경로 지정 하는 사용자에 게 요청 수입니다.

> [!IMPORTANT]
> 모든 Dll의 전체 경로 지정 해야 합니다. 파일을 로드 하는 경우 현재 디렉터리가 먼저 검색 됩니다. 파일의 경로 지정 하지 않으면 의도 하지 않은 파일을 로드할 수 있습니다. 이 문제를 방지 하는 또 다른 방법은 사용 하는 것은 [/DEPENDENTLOADFLAG](reference/dependentloadflag.md) 링커 옵션입니다.

## <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.

- [DLL에 실행 파일 링크](linking-an-executable-to-a-dll.md#linking-implicitly)

- [DLL에 실행 파일 링크](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>추가 정보

- [동적 연결 라이브러리 순서](/windows/desktop/Dlls/dynamic-link-library-search-order)

- [FreeLibrary 및 AfxFreeLibrary](freelibrary-and-afxfreelibrary.md)

- [GetProcAddress](getprocaddress.md)

## <a name="see-also"></a>참고자료

- [Visual C++의 DLL](dlls-in-visual-cpp.md)
