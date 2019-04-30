---
title: call_in_appdomain 함수
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- call_in_appdomain
helpviewer_keywords:
- call_in_appdomain function
ms.assetid: 9a1a5026-b76b-4cae-a3d4-29badeb9db9c
ms.openlocfilehash: a7ee0ef9c98ee940ab810abd82f6220da95d7346
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62351497"
---
# <a name="callinappdomain-function"></a>call_in_appdomain 함수

지정 된 응용 프로그램 도메인에서 함수를 실행합니다.

## <a name="syntax"></a>구문

```
template <typename ArgType1, ...typename ArgTypeN>
void call_in_appdomain(
   DWORD appdomainId,
   void (*voidFunc)(ArgType1, ...ArgTypeN) [ ,
   ArgType1 arg1,
   ...
   ArgTypeN argN ]
);
template <typename RetType, typename ArgType1, ...typename ArgTypeN>
RetType call_in_appdomain(
   DWORD appdomainId,
   RetType (*nonvoidFunc)(ArgType1, ...ArgTypeN) [ ,
   ArgType1 arg1,
   ...
   ArgTypeN argN ]
);
```

#### <a name="parameters"></a>매개 변수

*appdomainId*<br/>
함수를 호출 하는 appdomain 합니다.

*voidFunc*<br/>
에 대 한 포인터를 `void` N 매개 변수를 사용 하는 함수 (0 < = N < = 15).

*nonvoidFunc*<br/>
이외에 대 한 포인터`void` N 매개 변수를 사용 하는 함수 (0 < = N < = 15).

*arg1...argN*<br/>
0에 전달할 매개 변수가 15 ~ `voidFunc` 또는 `nonvoidFunc` 다른 appdomain에서.

## <a name="return-value"></a>반환 값

실행 결과 `voidFunc` 또는 `nonvoidFunc` 지정 된 응용 프로그램 도메인입니다.

## <a name="remarks"></a>설명

함수의 인수를 전달할 `call_in_appdomain` CLR 형식이 아니어야 합니다.

## <a name="example"></a>예제

```
// msl_call_in_appdomain.cpp
// compile with: /clr

// Defines two functions: one takes a parameter and returns nothing,
// the other takes no parameters and returns an int.  Calls both
// functions in the default appdomain and in a newly-created
// application domain using call_in_appdomain.

#include <msclr\appdomain.h>

using namespace System;
using namespace msclr;

void PrintCurrentDomainName( char* format )
{
   String^ s = gcnew String(format);
   Console::WriteLine( s, AppDomain::CurrentDomain->FriendlyName );
}

int GetDomainId()
{
   return AppDomain::CurrentDomain->Id;
}

int main()
{
   AppDomain^ appDomain1 = AppDomain::CreateDomain( "First Domain" );

   call_in_appdomain( AppDomain::CurrentDomain->Id,
                   &PrintCurrentDomainName,
                   (char*)"default appdomain: {0}" );
   call_in_appdomain( appDomain1->Id,
                   &PrintCurrentDomainName,
                   (char*)"in appDomain1: {0}" );

   int id;
   id = call_in_appdomain( AppDomain::CurrentDomain->Id, &GetDomainId );
   Console::WriteLine( "default appdomain id = {0}", id );
   id = call_in_appdomain( appDomain1->Id, &GetDomainId );
   Console::WriteLine( "appDomain1 id = {0}", id );
}
```

## <a name="output"></a>출력

```
default appdomain: msl_call_in_appdomain.exe
in appDomain1: First Domain
default appdomain id = 1
appDomain1 id = 2
```

## <a name="requirements"></a>요구 사항

**헤더 파일** \<msclr\appdomain.h >

**Namespace** msclr