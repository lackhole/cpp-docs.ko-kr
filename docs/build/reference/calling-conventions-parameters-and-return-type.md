---
title: 호출 규칙, 매개 변수, 반환 형식
ms.date: 02/13/2019
helpviewer_keywords:
- calling conventions, helper functions
- helper functions, calling conventions
- helper functions, return types
ms.assetid: 0ffa4558-6005-4803-be95-7a8ec8837660
ms.openlocfilehash: a85825eb49b1f8faab7862e902b226c1c1fb6d58
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62294709"
---
# <a name="calling-conventions-parameters-and-return-type"></a>호출 규칙, 매개 변수, 반환 형식

도우미 루틴의 프로토타입은 다음과 같습니다.

```
FARPROC WINAPI __delayLoadHelper2(
    PCImgDelayDescr pidd,
    FARPROC * ppfnIATEntry
);
```

### <a name="parameters"></a>매개 변수

*pidd*<br/>
A `const` 에 대 한 포인터를 `ImgDelayDescr` 포함 하는 다양 한 가져오기 관련 데이터, 바인딩 정보에 대 한 타임 스탬프 및 설명자 콘텐츠에 대 한 추가 정보를 제공 하는 특성 집합의 오프셋입니다. 현재는 하나의 특성만 `dlattrRva`를 나타내는 설명자의 주소가 상대 가상 주소입니다. 자세한 내용은 참조의 선언과 *delayimp.h*합니다.

정의 대해서는 `PCImgDelayDescr` 구조체를 참조 하십시오 [구조체 및 상수 정의](structure-and-constant-definitions.md)합니다.

*ppfnIATEntry*<br/>
가져온 함수의 주소로 업데이트 되는 지연 로드 가져오기 주소 테이블 (IAT)의 슬롯 포인터입니다. 도우미 루틴은이 위치에 반환 되는 동일한 값을 저장 해야 합니다.

## <a name="expected-return-values"></a>예상 반환 값

함수에 성공하면 가져온 함수의 주소가 반환됩니다.

함수에 실패하면 예외가 발생하고 0이 반환됩니다. 다음과 같은 3가지 형식의 예외가 발생할 수 있습니다.

- 잘못된 매개 변수. `pidd`의 특성을 제대로 지정하지 않으면 발생합니다.

- 지정된 DLL에서 실패한 `LoadLibrary`

- `GetProcAddress`의 실패

이러한 예외를 처리 해야 하는 것입니다.

## <a name="remarks"></a>설명

도우미 함수의 호출 규칙은 `__stdcall`입니다. 반환 값 유형의 관련이 관련 없으므로 FARPROC가 사용 됩니다. 이 함수에는 C 링크가 있습니다.

도우미 루틴을 알림 후크로 사용하지 않으려는 경우에는 지연 로드 도우미의 반환 값을 전달된 함수 포인터 위치에 저장해야 합니다. 이러한 경우 사용자 코드가 반환할 적절한 함수 포인터 찾기를 담당합니다. 그러면 링커가 생성한 썽크 코드가 해당 반환 값을 가져오기의 실제 대상으로 인식하여 해당 대상으로 직접 이동합니다.

## <a name="sample"></a>샘플

다음 코드는 간단한 후크 함수를 구현하는 방법을 보여줍니다.

```C
FARPROC WINAPI delayHook(unsigned dliNotify, PDelayLoadInfo pdli)
{
    switch (dliNotify) {
        case dliStartProcessing :

            // If you want to return control to the helper, return 0.
            // Otherwise, return a pointer to a FARPROC helper function
            // that will be used instead, thereby bypassing the rest
            // of the helper.

            break;

        case dliNotePreLoadLibrary :

            // If you want to return control to the helper, return 0.
            // Otherwise, return your own HMODULE to be used by the
            // helper instead of having it call LoadLibrary itself.

            break;

        case dliNotePreGetProcAddress :

            // If you want to return control to the helper, return 0.
            // If you choose you may supply your own FARPROC function
            // address and bypass the helper's call to GetProcAddress.

            break;

        case dliFailLoadLib :

            // LoadLibrary failed.
            // If you don't want to handle this failure yourself, return 0.
            // In this case the helper will raise an exception
            // (ERROR_MOD_NOT_FOUND) and exit.
            // If you want to handle the failure by loading an alternate
            // DLL (for example), then return the HMODULE for
            // the alternate DLL. The helper will continue execution with
            // this alternate DLL and attempt to find the
            // requested entrypoint via GetProcAddress.

            break;

        case dliFailGetProc :

            // GetProcAddress failed.
            // If you don't want to handle this failure yourself, return 0.
            // In this case the helper will raise an exception
            // (ERROR_PROC_NOT_FOUND) and exit.
            // If you choose you may handle the failure by returning
            // an alternate FARPROC function address.

            break;

        case dliNoteEndProcessing :

            // This notification is called after all processing is done.
            // There is no opportunity for modifying the helper's behavior
            // at this point except by longjmp()/throw()/RaiseException.
            // No return value is processed.

            break;

        default :

            return NULL;
    }

    return NULL;
}

/*
and then at global scope somewhere
const PfnDliHook __pfnDliNotifyHook2 = delayHook;
*/
```

## <a name="see-also"></a>참고자료

[도우미 함수 이해](understanding-the-helper-function.md)