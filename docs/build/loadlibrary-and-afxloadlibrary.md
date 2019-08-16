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
ms.openlocfilehash: c7700dd865e320686a2ad8bd036f207b9ecee6ac
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493218"
---
# <a name="loadlibrary-and-afxloadlibrary"></a>LoadLibrary 및 AfxLoadLibrary

[LoadLibraryExA](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexa) 또는 [LoadLibraryExW](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw) (또는 [AfxLoadLibrary](../mfc/reference/application-information-and-management.md#afxloadlibrary)) 호출을 처리 하 여 DLL에 명시적으로 연결 합니다. 함수가 성공 하면 지정 된 DLL을 호출 프로세스의 주소 공간에 매핑하고 명시적 링크 (예: `GetProcAddress` 및 `FreeLibrary`)의 다른 함수와 함께 사용할 수 있는 dll에 대 한 핸들을 반환 합니다.

`LoadLibrary`암시적 링크에 사용 되는 것과 동일한 검색 시퀀스를 사용 하 여 DLL을 찾으려고 시도 합니다. 시스템에서 DLL을 찾을 수 없거나 진입점 함수가 FALSE를 반환 하는 경우는 NULL `LoadLibrary` 을 반환 합니다. 호출에서 `LoadLibrary` 호출 프로세스의 주소 공간에 이미 매핑된 dll 모듈을 지정 하는 경우 함수는 dll의 핸들을 반환 하 고 모듈의 참조 횟수를 증가 시킵니다.

DLL에 진입점 함수가 있는 경우 운영 체제는를 호출한 `LoadLibrary`스레드의 컨텍스트에서 함수를 호출 합니다. 에 `LoadLibrary` 대 한 이전 호출로 인해 `FreeLibrary` 함수에 대 한 해당 호출이 없어 DLL이 프로세스에 이미 연결 되어 있는 경우 진입점 함수가 호출 되지 않습니다.

Mfc 확장 dll을 로드 하는 mfc 응용 프로그램의 경우 `AfxLoadLibrary` `LoadLibrary`대신를 사용 하는 것이 좋습니다. `AfxLoadLibrary`는를 호출 `LoadLibrary`하기 전에 스레드 동기화를 처리 합니다. 에 대 `AfxLoadLibrary` 한 인터페이스 (함수 프로토타입)는와 `LoadLibrary`동일 합니다.

Windows에서 DLL을 로드할 수 없는 경우 프로세스에서 오류 복구를 시도할 수 있습니다. 예를 들어 프로세스에서 사용자에 게 오류를 알리고 DLL에 대 한 다른 경로를 지정 하도록 요청할 수 있습니다.

> [!IMPORTANT]
> 모든 Dll의 전체 경로를 지정 해야 합니다. 파일이 로드 될 때 현재 디렉터리가 먼저 검색 됩니다. 파일의 경로를 한정 하지 않으면 파일 경로를 로드할 수 없습니다. 이를 방지 하는 또 다른 방법은 [/DEPENDENTLOADFLAG](reference/dependentloadflag.md) 링커 옵션을 사용 하는 것입니다.

## <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.

- [DLL에 실행 파일 링크](linking-an-executable-to-a-dll.md#linking-implicitly)

- [DLL에 실행 파일 링크](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>추가 정보

- [동적 연결 라이브러리 검색 순서](/windows/win32/Dlls/dynamic-link-library-search-order)

- [FreeLibrary 및 AfxFreeLibrary](freelibrary-and-afxfreelibrary.md)

- [GetProcAddress](getprocaddress.md)

## <a name="see-also"></a>참고자료

- [Visual Studio에서 C/C++ DLL 만들기](dlls-in-visual-cpp.md)
