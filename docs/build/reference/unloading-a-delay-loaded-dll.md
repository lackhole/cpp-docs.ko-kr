---
title: 지연 로드된 DLL 언로드
ms.date: 11/04/2016
helpviewer_keywords:
- __FUnloadDelayLoadedDLL2
- delayed loading of DLLs, unloading
ms.assetid: 6463bc71-020e-4aff-a4ca-90360411c54e
ms.openlocfilehash: 284a9cb9268c8c794379c6a5468b0f2b9092b7d0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62317460"
---
# <a name="unloading-a-delay-loaded-dll"></a>지연 로드된 DLL 언로드

기본적으로 제공 되는 지연 로드 도우미 경우 지연 로드 설명자에 대 한 포인터와는 원래 주소 IAT (가져오기 테이블)의 복사본이 pUnloadIAT 필드를 확인 합니다. 그렇다면 가져오기 지연 설명자에 목록에 대 한 포인터에 저장 됩니다. 이 도우미 함수를 이름에 명시적으로 DLL 언로드를 지원 하 여 DLL을 찾을 수 있습니다.

다음은 연결된 구조 및 지연 로드 DLL의 명시적 언로드에 대 한 함수입니다.

```cpp
//
// Unload support from delayimp.h
//

// routine definition; takes a pointer to a name to unload

ExternC
BOOL WINAPI
__FUnloadDelayLoadedDLL2(LPCSTR szDll);

// structure definitions for the list of unload records
typedef struct UnloadInfo * PUnloadInfo;
typedef struct UnloadInfo {
    PUnloadInfo     puiNext;
    PCImgDelayDescr pidd;
    } UnloadInfo;

// from delayhlp.cpp
// the default delay load helper places the unloadinfo records in the
// list headed by the following pointer.
ExternC
PUnloadInfo __puiHead;
```

UnloadInfo 구조를 사용 하 여 구현 됩니다는 C++ 를 사용 하는 클래스 **LocalAlloc** 및 **LocalFree** 해당 연산자로 구현 **새** 연산자**삭제** 각각. 이러한 옵션은 목록의 헤드 __puiHead 사용 하는 표준 링크 목록에 보관 됩니다.

호출 __FUnloadDelayLoadedDLL 이름을 찾으려면 하려고 합니다. 로드 된 Dll (정확히 일치 하는 필수임) 목록을 제공 합니다. 발견 경우 pUnloadIAT의 IAT 복사본은 복사 맨 썽크 포인터를 복원 하려면 실행 중인 IAT 통해 라이브러리를 사용 하 여 해제 됩니다 **FreeLibrary**, 일치 하는 **UnloadInfo** 레코드에서 연결이 해제 됩니다 목록 삭제 하 고 TRUE 반환 됩니다.

함수 __FUnloadDelayLoadedDLL2 인수는 대/소문자 구분 합니다. 예를 들어 지정 하면 됩니다.

```cpp
__FUnloadDelayLoadedDLL2("user32.DLL");
```

및 not을 추가 합니다.

```cpp
__FUnloadDelayLoadedDLL2("User32.DLL");.
```

## <a name="see-also"></a>참고자료

[도우미 함수 이해](understanding-the-helper-function.md)
