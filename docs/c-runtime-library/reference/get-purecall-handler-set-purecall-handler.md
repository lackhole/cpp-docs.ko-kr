---
title: _get_purecall_handler, _set_purecall_handler
ms.date: 11/04/2016
apiname:
- _set_purecall_handler
- _set_purecall_handler_m
- _get_purecall_handler
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _set_purecall_handler
- _set_purecall_handler_m
- set_purecall_handler_m
- set_purecall_handler
- stdlib/_set_purecall_handler
- stdlib/_get_purecall_handler
- _get_purecall_handler
helpviewer_keywords:
- _set_purecall_handler function
- set_purecall_handler function
- purecall_handler
- set_purecall_handler_m function
- _purecall_handler
- _set_purecall_handler_m function
- _get_purecall_handler function
ms.assetid: 2759b878-8afa-4129-86e7-72afc2153d9c
ms.openlocfilehash: 0009b4bc1c7bf70bd84b9a82ecdc8643789e8164
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287402"
---
# <a name="getpurecallhandler-setpurecallhandler"></a>_get_purecall_handler, _set_purecall_handler

순수 가상 함수 호출에 대한 오류 처리기를 가져오거나 설정합니다.

## <a name="syntax"></a>구문

```cpp
typedef void (__cdecl* _purecall_handler)(void);
_purecall_handler __cdecl _get_purecall_handler(void);
_purecall_handler __cdecl _set_purecall_handler(
   _purecall_handler function
);
```

### <a name="parameters"></a>매개 변수

*function*<br/>
순수 가상 함수 호출 시 호출되는 함수입니다. A **_purecall_handler** 함수에 void 반환 형식이 있어야 합니다.

## <a name="return-value"></a>반환 값

이전 **_purecall_handler**합니다. 반환 **nullptr** 되었으면 이전 처리기입니다.

## <a name="remarks"></a>설명

합니다 **_get_purecall_handler** 하 고 **_set_purecall_handler** 함수는 Microsoft 고유의 및에 적용 됩니다 C++ 코드입니다.

순수 가상 함수에 대한 호출은 구현이 없으므로 오류입니다. 기본적으로 순수 가상 함수를 호출하면 컴파일러는 오류 처리기 함수를 호출하는 코드를 생성하므로 프로그램이 종료됩니다. 순수 가상 함수 호출을 위해 고유한 오류 처리기 함수를 설치하여 디버깅 또는 보고용으로 이러한 호출을 catch할 수 있습니다. 사용자 고유의 오류 처리기를 사용 하려면 포함 된 함수를 만듭니다는 **_purecall_handler** 서명을 사용 하 여 **_set_purecall_handler** 현재 처리기를 확인 합니다.

하나만 있기 때문에 **_purecall_handler** 호출 하는 경우 각 프로세스에 대 한 **_set_purecall_handler** 모든 스레드가 즉시 영향입니다. 스레드의 마지막 호출자가 처리기를 설정합니다.

기본 동작을 복원 하려면 호출 **_set_purecall_handler** 사용 하 여를 **nullptr** 인수입니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_get_purecall_handler**, **_set_purecall_handler**|\<cstdlib> 또는 \<stdlib.h>|

호환성에 대한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```cpp
// _set_purecall_handler.cpp
// compile with: /W1
#include <tchar.h>
#include <stdio.h>
#include <stdlib.h>

class CDerived;
class CBase
{
public:
   CBase(CDerived *derived): m_pDerived(derived) {};
   ~CBase();
   virtual void function(void) = 0;

   CDerived * m_pDerived;
};

class CDerived : public CBase
{
public:
   CDerived() : CBase(this) {};   // C4355
   virtual void function(void) {};
};

CBase::~CBase()
{
   m_pDerived -> function();
}

void myPurecallHandler(void)
{
   printf("In _purecall_handler.");
   exit(0);
}

int _tmain(int argc, _TCHAR* argv[])
{
   _set_purecall_handler(myPurecallHandler);
   CDerived myDerived;
}
```

```Output
In _purecall_handler.
```

## <a name="see-also"></a>참고자료

[오류 처리](../../c-runtime-library/error-handling-crt.md)<br/>
[_purecall](purecall.md)<br/>
