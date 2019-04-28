---
title: 알림 후크
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, notification hooks
ms.assetid: e9c291ed-2f2d-4319-a171-09800625256f
ms.openlocfilehash: 884d8e8479b7cad28d99e19adfac4d05dbeec5f5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320476"
---
# <a name="notification-hooks"></a>알림 후크

알림 후크 도우미 루틴에 다음 작업을 수행 하는 바로 전에 호출 됩니다.

- 라이브러리에 저장 된 핸들을 참조 하는 경우 이미 로드 되었음을 확인 합니다.

- **LoadLibrary** DLL의 로드를 시도 하기 위해 호출 됩니다.

- **GetProcAddress** 프로시저의 주소를 가져오려고 시도 하기 위해 호출 됩니다.

- 지연 가져오기 부하 썽크를 반환 합니다.

알림 후크를 사용 됩니다.

- 포인터의 새 정의 제공 하 여 **__pfnDliNotifyHook2** 알림을 수신 하는 고유한 함수를 가리키도록 하 여 초기화 합니다.

   \-또는-

- 포인터를 설정 하 여 **__pfnDliNotifyHook2** 프로그램이 DLL에 대 한 모든 호출 지연 로드 전에 후크 함수입니다.

알림 **dliStartProcessing**, 후크 함수를 반환할 수 있습니다.

- NULL

   기본 도우미 DLL의 로드를 처리합니다. 정보 제공을 위해서만 호출 하는 데 유용 합니다.

- 함수 포인터

   기본 지연 로드 처리를 무시 합니다. 이렇게 하면 고유한 부하 처리기를 제공할 수 있습니다.

알림 **dliNotePreLoadLibrary**, 후크 함수를 반환할 수 있습니다.

- 정보 알림만 원하는 경우 0입니다.

- 자체 DLL을 로드 하는 경우 로드 된 DLL에 대 한 HMODULE 합니다.

알림 **dliNotePreGetProcAddress**, 후크 함수를 반환할 수 있습니다.

- 정보 알림만 원하는 경우 0입니다.

- 후크 함수 주소 자체를 가져오는 경우 가져온된 함수의 주소입니다.

알림 **dliNoteEndProcessing**를 후크 함수의 반환 값은 무시 됩니다.

This이 포인터 (0이 아닌)으로 초기화 되 면 지연 로드 도우미를 실행 하는 동안 특정 알림 지점에서 함수를 호출 합니다. 함수 포인터에는 다음 정의가 있습니다.

```C
// The "notify hook" gets called for every call to the
// delay load helper.  This allows a user to hook every call and
// skip the delay load helper entirely.
//
// dliNotify == {
//  dliStartProcessing |
//  dliNotePreLoadLibrary  |
//  dliNotePreGetProc |
//  dliNoteEndProcessing}
//  on this call.
//
ExternC
PfnDliHook   __pfnDliNotifyHook2;

// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}
ExternC
PfnDliHook   __pfnDliFailureHook2;
```

알림을 전달 된 **DelayLoadInfo** 알림 값과 함께 후크 함수에 구조체. 이 데이터는 지연 로드 도우미 루틴에서 사용 되는 동일 합니다. 알림 값에 정의 된 값 중 하나가 됩니다 [구조체 및 상수 정의](structure-and-constant-definitions.md)합니다.

## <a name="see-also"></a>참고자료

[오류 처리 및 알림](error-handling-and-notification.md)
