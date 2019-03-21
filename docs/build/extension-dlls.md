---
title: 확장명 DLL
ms.date: 11/04/2016
f1_keywords:
- afxdll
helpviewer_keywords:
- memory [C++], DLLs
- MFC extension DLLs [C++]
- AFXDLL library
- shared resources [C++]
- MFC DLLs [C++], MFC extension DLLs
- DLLs [C++], extension
- shared DLL versions [C++]
- resource sharing [C++]
- extension DLLs [C++]
- extension DLLs [C++], about MFC extension DLLs
ms.assetid: f69ac3d4-e474-4b1c-87a1-6738843a135c
ms.openlocfilehash: eca33b60b8fa6ba812bf5fa68520f51ceb1d164b
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820444"
---
# <a name="mfc-extension-dlls"></a>MFC 확장명 Dll

MFC 확장 DLL은 일반적으로 기존 Microsoft Foundation Class 라이브러리 클래스에서 파생 된 다시 사용할 수 있는 클래스를 구현 하는 DLL입니다.

MFC 확장 DLL은 다음 기능 및 요구 사항에 있습니다.

- 클라이언트 실행 파일을 컴파일하면 MFC 응용 프로그램 해야 `_AFXDLL` 정의 합니다.

- MFC 확장 DLL에서 MFC에 동적으로 연결 된 기본 MFC DLL도 사용할 수 있습니다.

- MFC 확장명 Dll로 컴파일해야 `_AFXEXT` 정의 합니다. 이렇게 하면 `_AFXDLL` 도 정의 하 고 적절 한 선언을 MFC 헤더 파일에서 로드 되는 되도록 합니다. 또한 `AFX_EXT_CLASS` 란 `__declspec(dllexport)` DLL을 작성 하는 동안 필요한 경우이 매크로 사용 하는 MFC 확장 DLL의에서 클래스를 선언 하는 합니다.

- MFC 확장명 Dll에서 파생 된 클래스를 인스턴스화하면 안 `CWinApp`, 있지만,이 개체를 제공 하는 클라이언트 응용 프로그램 (또는 DLL)에 의존 해야 합니다.

- 그러나 MFC 확장명 Dll 제공 해야는 `DllMain` 작동 하 고 필요한 초기화를 수행 합니다.

확장명 Dll은 MFC (라고도 하는 MFC의 공유 버전)의 동적 연결 라이브러리 버전을 사용 하 여 빌드됩니다. 만 MFC 실행 파일 (응용 프로그램 또는 기본 MFC Dll) 공유 버전의 MFC 사용 하 여 기본 제공 되는 MFC 확장 DLL을 사용할 수 있습니다. 클라이언트 응용 프로그램 및 MFC 확장명 DLL MFCx0.dll의 동일한 버전을 사용 해야 합니다. MFC 확장 DLL MFC에서 새 사용자 지정 클래스를 파생 시킬 수 있으며 다음이 확장된 버전의 MFC DLL을 호출 하는 응용 프로그램에 제공할 수 있습니다.

또한 확장 Dll 응용 프로그램과 DLL 간에 MFC 파생 개체를 전달 하는 데 사용할 수 있습니다. 전달 된 개체에 연결 된 멤버 함수는 개체가 만들어진 모듈에 존재 합니다. 공유 DLL 버전의 MFC 사용 하는 경우 이러한 함수를 적절 하 게 내보내므로 MFC 자유롭게 전달할 수 있습니다 또는 응용 프로그램 및 MFC 확장 Dll 로드 간에 MFC 파생 개체 포인터입니다.

MFC 확장 DLL 공유 버전의 MFC 사용 하 여 동일한 방식으로 응용 프로그램의 MFC 공유 DLL 버전을 사용 하 여 몇 가지 사항을 추가로 고려해 야 합니다.

- 없기는 `CWinApp`-파생 개체입니다. 사용 하 여 작동 해야 합니다는 `CWinApp`-클라이언트 응용 프로그램의 개체를 파생 합니다. 이 기본 메시지 펌프, 유휴 루프 등과 클라이언트 응용 프로그램에서 소유 하는 것을 의미 합니다.

- 호출한 `AfxInitExtensionModule` 에서 해당 `DllMain` 함수입니다. 이 함수의 반환 값을 검사 해야 합니다. 값이 0이 반환 되 면 `AfxInitExtensionModule`에서 0을 반환 하면 `DllMain` 함수입니다.

- 만듭니다는 **그렇지 않으면 CDynLinkLibrary** MFC 확장명 DLL 내보내려는 경우 초기화 하는 동안 개체 `CRuntimeClass` 개체 또는 응용 프로그램에는 리소스입니다.

MFC 버전 4.0이이 유형의 DLL AFXDLL 호출 되었습니다. AFXDLL 참조는 `_AFXDLL` DLL을 빌드할 때 정의 된 전처리기 기호입니다.

MFC의 공유 버전에 대 한 가져오기 라이브러리에 설명 된 규칙에 따라 라고 [MFC Dll의 명명 규칙](../mfc/mfc-library-versions.md#mfc-static-library-naming-conventions)합니다. Visual c + + MFC Dll을 더한 숫자의 비 MFC Dll 응용 프로그램을 사용 하 여 배포 및 사용할 수 있는 미리 빌드된 버전을 제공 합니다. 이러한 Program Files\Microsoft Visual Studio 폴더에 설치 되는 Redist.txt에 나와 있습니다.

.Def 파일을 사용 하 여 내보내려는 경우 헤더 파일의 시작과 끝에 다음 코드를 추가 합니다.

```cpp
#undef AFX_DATA
#define AFX_DATA AFX_EXT_DATA
// <body of your header file>
#undef AFX_DATA
#define AFX_DATA
```

이 네 줄 MFC 확장 DLL 용 코드가 올바르게 컴파일 되었는지 확인 합니다. 이러한 네 줄 DLL 컴파일 또는 링크가 올바르지 않을 수 있습니다.

MFC를 전달 해야 할 경우 MFC DLL, DLL 간에 MFC 파생 개체 포인터는 MFC 확장 DLL을 이어야 합니다. 전달 된 개체에 연결 된 멤버 함수는 개체가 만들어진 모듈에 존재 합니다. 공유 DLL 버전의 MFC 사용 하는 경우 이러한 함수를 적절 하 게 내보내므로 MFC 자유롭게 전달할 수 있습니다 또는 응용 프로그램 및 MFC 확장 Dll 로드 간에 MFC 파생 개체 포인터입니다.

C + + 이름 꾸미기 및 내보내기 문제로 인해 MFC 확장 내보내기 목록 DLL 수 있습니다 다른 플랫폼에 대 한 동일한 DLL의 디버그 버전과 소매 간에 다릅니다. 소매 MFCx0.dll에 약 2,000 내보낸 진입점이 있습니다. 디버그 MFCx0D.dll에 약 3,000 내보낸된 진입점이 있습니다.

## <a name="memory-management"></a>메모리 관리

MFCx0.dll과 모든 MFC 확장명 Dll을 클라이언트 응용 프로그램의 주소 공간에 로드 사용 하 여 동일한 메모리 할당자, 리소스 로드 및 기타 MFC 전역 상태 동일한 응용 프로그램 처럼. 비 MFC DLL 라이브러리와 기본 MFC Dll이 정반대의 작업을 수행 하며 자체 메모리 풀에서 각 DLL 할당 하기 때문에 유효 합니다.

MFC 확장 DLL이 메모리를 할당 하는 경우 해당 메모리가 다른 응용 프로그램에서 할당 된 개체를 사용 하 여 자유롭게 혼합 될 수 있습니다. 또한 동적으로 MFC에 링크 되는 응용 프로그램이 실패할 경우 보호는 운영 체제의 해당 DLL을 공유 하는 다른 MFC 응용 프로그램의 무결성을 유지 합니다.

마찬가지로 다른 전역 MFC 상태는 리소스를 로드 하려면 현재 실행 파일과 같은 클라이언트 응용 프로그램 및 모든 MFC 확장명 Dll 뿐만 아니라 자체 MFCx0.dll 간에 공유 됩니다.

## <a name="sharing-resources-and-classes"></a>공유 리소스 및 클래스

리소스 내보내기 리소스 목록을 통해 수행 됩니다. 각 응용 프로그램의 단일 연결 목록이 **그렇지 않으면 CDynLinkLibrary** 개체입니다. 대부분의 리소스를 로드 하는 표준 MFC 구현에서는 먼저 현재 리소스 모듈 확인 리소스를 볼 때 (`AfxGetResourceHandle`) 리소스를 찾을 수 없습니다 경우의 목록으로 이동 **그렇지 않으면 CDynLinkLibrary** 개체 요청된 된 리소스를 로드 하려고 합니다.

목록 walking 단점이 있습니다. 조금 저하 되 고 리소스 ID 범위 관리를 필요로 합니다. 여러 MFC 확장 Dll에 연결 하는 클라이언트 응용 프로그램을 DLL 인스턴스 핸들을 지정 하지 않고도 DLL에서 제공 하는 모든 리소스를 사용할 수 있는 이점이 있습니다. `AfxFindResourceHandle` API는 리소스 목록 탐색 하기 위한 지정 된 일치 항목을 검색할 합니다. 리소스의 종류와 이름을 사용 하 고 처음 발견 되는 리소스 핸들 (또는 NULL)를 반환 합니다.

함수를 사용 하 여 목록으로 이동 하 여만 특정 위치에서 리소스를 로드 하지 않으려면 `AfxGetResourceHandle` 고 `AfxSetResourceHandle` 이전 핸들을 저장 하 고 새 핸들을 설정 합니다. 클라이언트 응용 프로그램에 반환 하기 전에 이전 리소스 핸들을 복원 해야 합니다. 이 방법을 사용 하 여 명시적으로 메뉴를 로드 하는 예로, Testdll2.cpp MFC 샘플에서을 참조 하세요 [DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk)합니다.

MFC 이름 MFC 개체의 동적 생성이 비슷합니다. MFC 개체 deserialization 메커니즘이 해야 모든는 `CRuntimeClass` 개체를 등록 하 여 저장 된 순서에 따라 필요한 형식의 c + + 개체를 동적으로 만들어 다시 구성할 수 있습니다.

MFC 샘플 [DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk), 목록와 같습니다.

```
head ->   DLLHUSK.EXE   - or -   DLLHUSK.EXE
               |                      |
          TESTDLL2.DLL           TESTDLL2.DLL
               |                      |
          TESTDLL1.DLL           TESTDLL1.DLL
               |                      |
           MFCOxxD.DLL                |
               |                      |
           MFCDxxD.DLL                |
               |                      |
            MFCxxD.DLL            MFCxx.DLL
```

여기서 *xx* 는 버전 번호입니다; 예를 들어, 42 버전 4.2를 나타냅니다.

MFCxx.dll은 대개 마지막 리소스 및 클래스 목록에 있습니다. MFCxx.dll 모든 프롬프트 문자열을 포함 하 여 모든 표준 명령 Id에 대 한 표준 MFC 리소스를 포함 합니다. Dll 및 클라이언트 응용 프로그램은 표준 MFC 리소스의 자체 복사본 유지할 필요가 없으며 대신 MFCxx.dll의 공유 리소스에 의존 하 허용 목록의 끝에 배치 합니다.

클라이언트 응용 프로그램의 네임 스페이스에 모든 Dll의 클래스 이름과 리소스 병합 단점이 사용자 Id 또는 이름을 선택 하면 주의 해야 합니다.

합니다 [DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk) 샘플에서는 여러 헤더 파일을 사용 하 여 공유 리소스 네임 스페이스를 관리 합니다.

새 클래스를 파생할 수 MFC 확장 DLL를 각 응용 프로그램에 대 한 추가 데이터를 유지 해야 하는 경우 **그렇지 않으면 CDynLinkLibrary** 에서 만들어 및 `DllMain`합니다. DLL의 현재 응용 프로그램의 목록을 확인할 수 있습니다를 실행할 때 **그렇지 않으면 CDynLinkLibrary** 해당 특정 MFC 확장명 DLL에 대 한 찾을 개체입니다.

### <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.

- [MFC 확장 DLL 초기화](run-time-library-behavior.md#initializing-extension-dlls)

### <a name="what-do-you-want-to-know-more-about"></a>추가 정보

- [공유 리소스 파일 사용에 대 한 팁](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md)

- [MFC의 DLL 버전](../mfc/tn033-dll-version-of-mfc.md)

- [정적으로 MFC에 링크 된 기본 MFC Dll](regular-dlls-statically-linked-to-mfc.md)

- [동적으로 MFC에 링크 된 기본 MFC Dll](regular-dlls-dynamically-linked-to-mfc.md)

- [기본 MFC DLL에서 데이터베이스, OLE 및 소켓 MFC 확장명 DLL 사용](using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)

## <a name="see-also"></a>참고자료

[Visual C++의 DLL](dlls-in-visual-cpp.md)
