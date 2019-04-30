---
title: 정적으로 MFC에 링크 된 기본 MFC Dll
ms.date: 11/04/2016
helpviewer_keywords:
- regular MFC DLLs [C++]
- DLLs [C++], regular
- USRDLLs
- USRDLLs, statically linked to MFC
- statically linked DLLs [C++]
- regular MFC DLLs [C++], statically linked to MFC
ms.assetid: 2eed531c-726a-4b8a-b936-f721dc00a7fa
ms.openlocfilehash: 1f05b5e3c268935cf3161fb7184e04b3e3ea1446
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62314782"
---
# <a name="regular-mfc-dlls-statically-linked-to-mfc"></a>정적으로 MFC에 링크 된 기본 MFC Dll

일반 정적으로 MFC에 링크 된 MFC DLL은 MFC를 내부적으로 사용 하는 DLL 및 MFC 또는 비 MFC 실행 파일에서 DLL에서 내보낸된 함수를 호출할 수 있습니다. 이름에서 알 수 있듯이 이러한 종류의 DLL 정적 링크 라이브러리 버전의 MFC 사용 하 여 빌드됩니다. 함수는 일반적으로 일반 표준 C 인터페이스를 사용 하 여 MFC DLL에서에서 내보내집니다. 작성, 빌드 및 기본 MFC DLL을 사용 하는 방법의 예로, 샘플을 참조 하세요 [DLLScreenCap](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/DllScreenCap)합니다.

참고 용어 USRDLL 시각적 개체에 더 이상 사용 되는 C++ 설명서. 정적으로 MFC에 링크는 기본 MFC DLL은 이전의 usrdll과 같은 특징에 있습니다.

정적으로 MFC에 링크 된 기본 MFC DLL에는 다음 기능이 있습니다.

- 클라이언트 실행 파일은 Dll의 사용을 지 원하는 언어를 작성할 수 있습니다 (C C++, Pascal, Visual Basic 및 등); MFC 응용 프로그램 이어야 하는 것이 없습니다.

- DLL 응용 프로그램에서 사용 하는 것과 동일한 MFC 정적 연결 라이브러리에 연결할 수 있습니다. 더 이상 Dll에 대 한 정적 링크 라이브러리의 버전을 별도로 됩니다.

- MFC 버전 4.0 이전의 Usrdll 동일한 유형의 정적으로 MFC에 링크 된 기본 MFC Dll로 기능을 제공 합니다. 시각적 개체를 기준으로 C++ 버전 4.0 USRDLL 라는 용어는 사용 되지 않습니다.

정적으로 MFC에 링크 된 기본 MFC DLL에는 다음 요구 사항을 있습니다.

- DLL의이 형식에서 파생 된 클래스를 인스턴스화해야 `CWinApp`합니다.

- 이 유형의 DLL 사용의 `DllMain` MFC에서 제공 합니다. 모든 DLL 별 초기화 코드를 배치 합니다 `InitInstance` 멤버 함수, 종료 코드는 `ExitInstance` 일반적인 MFC 응용 프로그램과 같이 합니다.

- 용어 USRDLL는 사용 되지 않습니다, 경우에 정의 해야 "**_USRDLL**" 컴파일러 명령줄에서. 이 정의 선언에서에서 끌어온 구성 인 MFC 헤더 파일을 결정 합니다.

기본 MFC Dll 있어야를 `CWinApp`-파생 클래스 및 해당 응용 프로그램 클래스의 단일 개체 처럼 MFC 응용 프로그램입니다. 그러나 합니다 `CWinApp` DLL의 개체에는 기본 메시지 펌프와 마찬가지로 없는 `CWinApp` 응용 프로그램의 개체입니다.

`CWinApp::Run` 응용 프로그램 기본 메시지 펌프를 소유 하기 때문에 메커니즘을 DLL에 적용 되지 않습니다. 응용 프로그램의 기본 메시지 펌프를 호출 하는 DLL에서 내보낸 루틴을 호출 해야 경우 DLL 모덜리스 대화 상자 자체의 메인 프레임 창는 `CWinApp::PreTranslateMessage` DLL의 응용 프로그램 개체의 멤버 함수입니다.

이 함수는 예로, DLLScreenCap 샘플을 참조 하세요.

기호는 일반적으로 일반 표준 C 인터페이스를 사용 하 여 MFC DLL에서에서 내보내집니다. 기본 MFC DLL에서 내보내기 함수의 선언은 다음과 같이 보입니다.

```
extern "C" __declspec(dllexport) MyExportedFunction( );
```

기본 MFC DLL 내의 모든 메모리 할당 DLL; 내에서 유지 해야 DLL에 전달 하지 할지 호출 실행에서 다음 중 하나를 수신 합니다.

- MFC 개체에 대 한 포인터

- MFC에서 할당 된 메모리에 대 한 포인터

위의 작업이 호출 실행 파일과 DLL 간에 MFC 파생 개체를 전달할 필요 하거나 해야 할 경우에 MFC 확장 DLL 빌드해야 합니다.

포인터에 전달할 할당 된 메모리를 C 런타임 라이브러리를 통해 응용 프로그램과 DLL 간에 데이터의 복사본을 확인 하는 경우에 안전 합니다. 삭제 또는 이러한 포인터의 크기를 조정 하거나 하며 메모리의 복사본을 만들지 않고 사용 합니다.

정적으로 MFC에 링크 된 DLL 공유 MFC Dll에 동적으로 연결할 수 없습니다. 정적으로 MFC에 링크 된 DLL에 동적으로 다른 DLL;과 마찬가지로 응용 프로그램에 바인딩되어 다른 DLL과 마찬가지로 응용 프로그램에 연결합니다.

표준 MFC 정적 연결 라이브러리에 설명 된 규칙에 따라 라고 [MFC Dll에 대 한 명명 규칙](../mfc/mfc-library-versions.md#mfc-static-library-naming-conventions)합니다. 그러나 MFC 버전 3.0 이상에서 사용 하 여 것 더 이상에 연결 된 MFC 라이브러리의 버전을 링커로 수동으로 지정 해야 합니다. 대신 MFC 헤더 파일을 자동으로 확인 같은 올바른 버전의 MFC 라이브러리 링크에 따라 전처리기 정의  **\_디버그** 하거나 **_UNICODE**합니다. MFC 라이브러리의 특정 버전에 연결 하 여 링커가 /DEFAULTLIB 지시문을 추가 하는 MFC 헤더 파일.

## <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.

- [기본 MFC Dll 초기화](run-time-library-behavior.md#initializing-regular-dlls)

## <a name="what-do-you-want-to-know-more-about"></a>추가 정보

- [DLL의 일부로 MFC 사용](../mfc/tn011-using-mfc-as-part-of-a-dll.md)

- [기본 MFC DLL에서 데이터베이스, OLE 및 소켓 MFC 확장명 DLL 사용](using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)

- [MFC DLL 만들기](../mfc/reference/mfc-dll-wizard.md)

- [동적으로 MFC에 링크된 기본 MFC DLL](regular-dlls-dynamically-linked-to-mfc.md)

- [MFC 확장명 DLL](extension-dlls-overview.md)

## <a name="see-also"></a>참고자료

[DLL의 종류](kinds-of-dlls.md)
