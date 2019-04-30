---
title: '확장명 Dll: 개요'
ms.date: 11/04/2016
helpviewer_keywords:
- AFXDLL library
- MFC DLLs [C++], MFC extension DLLs
- DLLs [C++], extension
- shared DLL versions [C++]
- extension DLLs [C++], about MFC extension DLLs
ms.assetid: eb5e10b7-d615-4bc7-908d-e3e99b7b1d5f
ms.openlocfilehash: ab9b980cbb3e89eebee945e90c54f23d6717a1a4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62196731"
---
# <a name="mfc-extension-dlls-overview"></a>MFC 확장명 Dll: 개요

MFC 확장 DLL은 일반적으로 기존 Microsoft Foundation Class 라이브러리 클래스에서 파생 된 다시 사용할 수 있는 클래스를 구현 하는 DLL입니다. MFC 확장명 Dll은 MFC (라고도 하는 MFC의 공유 버전)의 동적 연결 라이브러리 버전을 사용 하 여 빌드됩니다. 만 MFC 실행 파일 (응용 프로그램 또는 기본 MFC Dll) 공유 버전의 MFC 사용 하 여 기본 제공 되는 MFC 확장 DLL을 사용할 수 있습니다. MFC 확장 DLL MFC에서 새 사용자 지정 클래스를 파생 시킬 수 있으며 다음이 확장된 버전의 MFC DLL을 호출 하는 응용 프로그램에 제공할 수 있습니다.

또한 확장 Dll 응용 프로그램과 DLL 간에 MFC 파생 개체를 전달 하는 데 사용할 수 있습니다. 전달 된 개체에 연결 된 멤버 함수는 개체가 만들어진 모듈에 존재 합니다. 공유 DLL 버전의 MFC 사용 하는 경우 이러한 함수를 적절 하 게 내보내므로 MFC 자유롭게 전달할 수 있습니다 또는 응용 프로그램 및 MFC 확장 Dll 로드 간에 MFC 파생 개체 포인터입니다.

MFC 확장 DLL의 기본 요구 사항을 충족 하는 DLL의 예로, MFC 샘플을 참조 하세요 [DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk)합니다. 특히 Testdll1.cpp 및 Testdll2.cpp 파일을 살펴봅니다.

참고 용어 AFXDLL 시각적 개체에 더 이상 사용 되는 C++ 설명서. MFC 확장 DLL은 이전의 AFXDLL와 동일한 특성.

## <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.

- [MFC 확장 DLL 초기화](run-time-library-behavior.md#initializing-extension-dlls)

## <a name="what-do-you-want-to-know-more-about"></a>추가 정보

- [MFC 확장명 DLL](extension-dlls.md)

- [기본 MFC DLL에서 데이터베이스, OLE 및 소켓 MFC 확장명 DLL 사용](using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)

- [비 MFC DLL: 개요](non-mfc-dlls-overview.md)

- [정적으로 MFC에 링크 된 기본 MFC Dll](regular-dlls-statically-linked-to-mfc.md)

- [동적으로 MFC에 링크 된 기본 MFC Dll](regular-dlls-dynamically-linked-to-mfc.md)

- [MFC DLL 만들기](../mfc/reference/mfc-dll-wizard.md)

## <a name="see-also"></a>참고자료

[DLL의 종류](kinds-of-dlls.md)
