---
title: 레지스트리 스크립팅 예
ms.date: 11/04/2016
helpviewer_keywords:
- scripting, examples
- registrar scripts [ATL]
- scripts, Registrar scripts
- registry, Registrar
ms.assetid: b6df80e1-e08b-40ee-9243-9b381b172460
ms.openlocfilehash: dffdd111d33d6fbd845e1534cdef1d5c8e1749d2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62275414"
---
# <a name="registry-scripting-examples"></a>레지스트리 스크립팅 예

이 항목의 스크립팅 예제 시스템 레지스트리에 키를 추가, 등록 기관 COM 서버를 등록, 여러 구문 분석 트리를 지정 하는 방법을 보여 줍니다.

## <a name="add-a-key-to-hkeycurrentuser"></a>HKEY_CURRENT_USER에 키 추가

다음 구문 분석 트리를 시스템 레지스트리에 단일 키를 추가 하는 간단한 스크립트를 보여 줍니다. 스크립트에서 키를 추가 하는 특히 `MyVeryOwnKey`를 `HKEY_CURRENT_USER`입니다. 기본 문자열 값을 할당 `HowGoesIt` 새 키:

```
HKEY_CURRENT_USER
{
    'MyVeryOwnKey' = s 'HowGoesIt'
}
```

이 스크립트를 여러 하위 키를 다음과 같이 정의 쉽게 확장할 수 있습니다.

```
HKCU
{
    'MyVeryOwnKey' = s 'HowGoesIt'
    {
        'HasASubkey'
        {
            'PrettyCool' = d '55'
            val 'ANameValue' = s 'WithANamedValue'
        }
    }
}
```

스크립트에 하위 키를 추가 하는 이제 `HasASubkey`를 `MyVeryOwnKey`입니다. 이 하위 키에 추가 모두를 `PrettyCool` 하위 키 (기본값 `DWORD` 55 값) 및 `ANameValue` 명명 된 값 (문자열 값을 사용 하 여 `WithANamedValue`).

##  <a name="_atl_register_the_registrar_com_server"></a> 등록 기관 COM 서버를 등록 합니다.

다음 스크립트를 자체 등록 기관 COM 서버를 등록합니다.

```
HKCR
{
    ATL.Registrar = s 'ATL Registrar Class'
    {
        CLSID = s '{44EC053A-400F-11D0-9DCD-00A0C90391D3}'
    }
    NoRemove CLSID
    {
        ForceRemove {44EC053A-400F-11D0-9DCD-00A0C90391D3} = s 'ATL Registrar Class'
        {
            ProgID = s 'ATL.Registrar'
            InprocServer32 = s '%MODULE%'
            {
                val ThreadingModel = s 'Apartment'
            }
        }
    }
}
```

런타임 시이 구문 분석 트리를 추가 합니다 `ATL.Registrar` 키를 `HKEY_CLASSES_ROOT`입니다. 이 새 키에 다음 it:

- 지정 `ATL Registrar Class` 키의 기본 문자열 값으로.

- 추가 `CLSID` 하위 키로 합니다.

- 지정 `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` 에 대 한 `CLSID`합니다. (이 값은 등록자의 사용에 대 한 CLSID `CoCreateInstance`.)

있으므로 `CLSID` 는 공유 되지 제거 해야 등록 취소 모드에서입니다. 문을 `NoRemove CLSID`를 나타내는 `CLSID` 등록 모드에서 열리고 등록 취소 모드에서는 무시 해야 합니다.

`ForceRemove` 키 다시 만들기 전에 키 및 모든 하위 키를 제거 하 여 정리 작업 함수를 제공 하는 문입니다. 이 하위 키의 이름을 변경 하는 경우에 유용할 수 있습니다. 이 스크립팅 예제 `ForceRemove` 있는지 검사 `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` 이미 있습니다. 이 경우 `ForceRemove`:

- 재귀적으로 삭제 `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` 및 모든 하위 키입니다.

- 다시 만듭니다 `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`합니다.

- 추가 `ATL Registrar Class` 에 대 한 기본 문자열 값으로 `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`입니다.

구문 분석 트리를 두 개의 새 하위 키를 지금 추가 `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`합니다. 첫 번째 키 `ProgID`, ProgID는 기본 문자열 값을 가져옵니다. 두 번째 키 `InprocServer32`, 기본 문자열 값을 가져옵니다 `%MODULE%`되는 전처리기 값의 섹션에서 설명한 [를 사용 하 여 대체 가능 매개 변수 (The 등록자 전처리기)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md),이 문서의. `InprocServer32` 명명 된 값을 가져옵니다 `ThreadingModel`, 문자열 값을 사용 하 여 `Apartment`입니다.

## <a name="specify-multiple-parse-trees"></a>여러 개의 구문 분석 트리를 지정 합니다.

스크립트에서 둘 이상의 구문 분석 트리를 지정 하려면 다른 끝에 트리를 배치 합니다. 다음 스크립트는 키를 추가 하는 예를 들어 `MyVeryOwnKey`를 둘 다에 대해 구문 분석 트리에 `HKEY_CLASSES_ROOT` 및 `HKEY_CURRENT_USER`:

```
HKCR
{
    'MyVeryOwnKey' = s 'HowGoesIt'
}
HKEY_CURRENT_USER
{
    'MyVeryOwnKey' = s 'HowGoesIt'
}
```

> [!NOTE]
> 등록자 스크립트에서 4k 최대 토큰 크기입니다. (토큰 구문에서 인식할 수 있는 요소입니다.) 이전 스크립트 예제에서는 `HKCR`, `HKEY_CURRENT_USER`, `'MyVeryOwnKey'`, 및 `'HowGoesIt'` 는 모든 토큰을 나타냅니다.

## <a name="see-also"></a>참고자료

[등록자 스크립트 만들기](../atl/creating-registrar-scripts.md)
