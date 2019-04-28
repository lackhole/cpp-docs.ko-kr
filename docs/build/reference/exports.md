---
title: EXPORTS
ms.date: 09/07/2018
f1_keywords:
- EXPORTS
helpviewer_keywords:
- EXPORTS .def file statement
ms.assetid: dbcd7579-b855-44c4-bd27-931e157657f7
ms.openlocfilehash: 33b70c680bfc3db24f5326a2027fa9ec4740e3f2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62271348"
---
# <a name="exports"></a>EXPORTS

함수 또는 데이터의 내보낸 이름이나 서수를 지정하는 하나 이상의 내보내기 정의 섹션에 대해 소개합니다. 각 정의는 별도의 줄에 있어야 합니다.

```DEF
EXPORTS
   definition
```

## <a name="remarks"></a>설명

첫 번째 *정의* 와 동일한 줄에 있을 수 있습니다는 `EXPORTS` 키워드 또는 후속 줄. .DEF 파일에는 `EXPORTS` 문이 한 개 이상 있을 수 있습니다.

내보내기에 대 한 구문을 *정의* 됩니다.

> *entryname*\[__=__*internal_name*|*other_module.exported_name*] \[**\@**_ordinal_ \[**NONAME**] ] \[ \[**PRIVATE**] | \[**DATA**] ]

*entryname* 내보내려는 함수 또는 변수 이름입니다. 이는 필수입니다. 내보내는 이름이 DLL의 이름과 다를 경우 내보내기의 이름을 DLL에서 사용 하 여 지정할 *internal_name*합니다. 예를 들어 DLL이 함수 `func1`을 내보내고 호출자가 이 함수를 `func2`로 사용하도록 하려는 경우 다음과 같이 지정할 수 있습니다.

```DEF
EXPORTS
   func2=func1
```

일부 다른 모듈에서 내보내는 이름이 인 경우 내보내기의 이름을 DLL에서 사용 하 여 지정할 *other_module.exported_name*합니다. 예를 들어 DLL이 함수 `other_module.func1`을 내보내고 호출자가 이 함수를 `func2`로 사용하도록 하려는 경우 다음과 같이 지정할 수 있습니다.

```DEF
EXPORTS
   func2=other_module.func1
```

내보내기를 사용 하 여 DLL의 서 수의 서 수로 내보내는 다른 모듈에서 내보내는 이름이 인 경우 지정할 *other_module*.__#__ *서*입니다. 예를 들어, DLL 있는 서 수 42 이므로 그대로 사용 하 여 호출자가 원하는 다른 모듈에서 함수를 내보내는 경우 `func2`를 지정할 수 있습니다.

```DEF
EXPORTS
   func2=other_module.#42
```

MSVC 컴파일러에 대 한 이름 데코레이션을 사용 하기 때문에 C++ 함수를 데코 레이트 된 이름을 사용 하거나 해야 *internal_name* 사용 하 여 내보낸된 함수를 정의할 `extern "C"` 소스 코드에서. 컴파일러에는 또한 C 함수를 사용 하 여 데코 레이트 합니다 [__stdcall](../../cpp/stdcall.md) 밑줄을 사용 하 여 규칙을 호출 (\_) 접두사 및 접미사 구성는 at 기호 (\@) 뒤에 바이트 수 (10 진수)가 붙은 인수 목록입니다.

컴파일러에서 생성 된 데코레이팅된 이름을 찾으려면 사용 합니다 [DUMPBIN](dumpbin-reference.md) 도구 또는 링커 [/map](map-generate-mapfile.md) 옵션입니다. 데코레이팅된 이름은 컴파일러별로 다릅니다. .DEF 파일의 데코레이팅된 이름을 내보내는 경우 DLL에 연결된 실행 파일도 동일한 버전의 컴파일러를 사용하여 빌드해야 합니다. 그래야 호출자의 데코레이팅된 이름이 .DEF 파일의 내보낸 이름과 일치하게 됩니다.

사용할 수 있습니다 \@ *서* 숫자 및 함수 이름이 아니라 DLL의 내보내기 테이블로 이동 되도록 합니다. 많은 Windows DLL은 서수를 내보내 레거시 코드를 지원합니다. Windows DLL의 크기를 최소화할 수 있기 때문에 16비트 Windows 코드에서는 서수를 사용하는 것이 일반적입니다. DLL 클라이언트에서 레거시 지원에 서수를 사용할 필요가 없는 경우 서수별 함수를 내보내지 않는 것이 좋습니다. .LIB 파일에는 서수와 함수 간의 매핑이 포함되므로 DLL을 사용하는 프로젝트에서 일반적으로 하는 것처럼 함수 이름을 사용할 수 있습니다.

선택적를 사용 하 여 **NONAME** 키워드를 서 수로만 결과 DLL의 내보내기 테이블의 크기를 줄일 수 있습니다. 그러나 사용 하려는 경우 [GetProcAddress](/windows/desktop/api/libloaderapi/nf-libloaderapi-getprocaddress) DLL에서 알고 있어야 합니다 서 수 있으므로 이름이 유효 하지 않게 됩니다.

선택적 키워드인 **사설** 방지 *entryname* 링크에 의해 생성 된 가져오기 라이브러리에 포함 되지 합니다. 이는 LINK에서도 생성한 이미지에서 내보내기에 영향을 미치지 않습니다.

선택적 키워드인 **데이터** 는 내보내기가 코드가 아니라 데이터가 임을 지정 합니다. 아래 예제는 `exported_global` 데이터 변수를 내보낼 수 있는 방법을 보여줍니다.

```DEF
EXPORTS
   exported_global DATA
```

다음은 정의를 내보내는 4가지 방법으로 권장 순서대로 나열되었습니다.

1. 합니다 [__declspec (dllexport)](../../cpp/dllexport-dllimport.md) 소스 코드의 키워드

1. .DEF 파일의 `EXPORTS` 문

1. [/내보내기](export-exports-a-function.md) LINK 명령의 사양

1. A [주석](../../preprocessor/comment-c-cpp.md) 폼의 소스 코드에 지시문 `#pragma comment(linker, "/export: definition ")`합니다. 다음 예제에서는 함수 선언 전에 #pragma comment 지시문 위치 `PlainFuncName` 데코 레이트 되지 않은 이름 및 `_PlainFuncName@4` 함수의 트 데코 레이 된 이름:

    ```cpp
    #pragma comment(linker, "/export:PlainFuncName=_PlainFuncName@4")
    BOOL CALLBACK PlainFuncName( Things * lpParams)
    ```

#Pragma 지시문을 데코 레이트 되지 않은 함수 이름을 내보내고에 빌드 구성에 따라 다른 내보내기 (예를 들어 32 비트 또는 64 비트 빌드) 해야 할 경우에 유용 합니다.

4가지 메서드 모두 동일한 프로그램에서 사용할 수 있습니다. LINK가 내보내기를 포함하는 프로그램을 빌드하는 경우 빌드에서 .EXP 파일을 사용하지 않는다면 가져오기 라이브러리도 만들게 됩니다.

다음은 EXPORTS 섹션의 예입니다.

```DEF
EXPORTS
   DllCanUnloadNow      @1          PRIVATE
   DllWindowName = WindowName       DATA
   DllGetClassObject    @4 NONAME   PRIVATE
   DllRegisterServer    @7
   DllUnregisterServer
```

.DEF 파일을 사용하여 DLL에서 변수를 내보낸 경우 변수에 대해 `__declspec(dllexport)`을 지정할 필요가 없습니다. 그러나 DLL을 사용하는 모든 파일에서는 데이터 선언 시 `__declspec(dllimport)`을 계속해서 사용해야 합니다.

## <a name="see-also"></a>참고자료

[모듈 정의 문의 규칙](rules-for-module-definition-statements.md)
