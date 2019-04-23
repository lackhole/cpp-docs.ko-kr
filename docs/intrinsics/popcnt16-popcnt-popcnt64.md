---
title: __popcnt16, __popcnt, __popcnt64
ms.date: 11/04/2016
f1_keywords:
- __popcnt64
- __popcnt
- __popcnt16
helpviewer_keywords:
- popcnt instruction
- __popcnt16
- __popcnt64
- __popcnt
ms.assetid: e525b236-adc8-42df-9b9b-8b7d8c245d3b
ms.openlocfilehash: d6cc9a0ce784ab79f5e4225675a082fc55bd53e7
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59037012"
---
# <a name="popcnt16-popcnt-popcnt64"></a>__popcnt16, __popcnt, __popcnt64

**Microsoft 전용**

개수를 하나의 비트 (채우기 수)를 16, 32 비트 또는 64 비트 부호 없는 정수입니다.

## <a name="syntax"></a>구문

```
unsigned short __popcnt16(
   unsigned short value
);
unsigned int __popcnt(
   unsigned int value
);
unsigned __int64 __popcnt64(
   unsigned __int64 value
);
```

#### <a name="parameters"></a>매개 변수

*값*<br/>
[in] 16-, 32 비트 또는 64 비트 부호 없는 정수 채우기 수를 사용 하도록 하겠습니다.

## <a name="return-value"></a>반환 값

하나의 비트 수는 `value` 매개 변수입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__popcnt16`|고급 비트 조작|
|`__popcnt`|고급 비트 조작|
|`__popcnt64`|64 비트 모드에서 고급 비트 조작 합니다.|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

각 이러한 내장 함수 생성을 `popcnt` 명령입니다. 32 비트 모드로 레지스터가 없습니다 64-bit 범용, 따라서 64 비트 이상 `popcnt`합니다.

에 대 한 하드웨어 지원을 확인 하는 `popcnt` 명령을 호출 합니다 `__cpuid` 포함 된 내장 함수 `InfoType=0x00000001` 23 많은 확인 및 `CPUInfo[2] (ECX)`합니다. 이 비트는 그렇지 않은 경우 명령 지원 되 면 1과 0입니다. 경우 코드를 실행 하면 사용 하 여이 내장 함수를 지원 하지 않는 하드웨어를 `popcnt` 명령 결과 예측할 수 없습니다.

## <a name="example"></a>예제

```
#include <iostream>
#include <intrin.h>
using namespace std;

int main()
{
  unsigned short us[3] = {0, 0xFF, 0xFFFF};
  unsigned short usr;
  unsigned int   ui[4] = {0, 0xFF, 0xFFFF, 0xFFFFFFFF};
  unsigned int   uir;

  for (int i=0; i<3; i++) {
    usr = __popcnt16(us[i]);
    cout << "__popcnt16(0x" << hex << us[i] << ") = " << dec << usr << endl;
  }

  for (int i=0; i<4; i++) {
    uir = __popcnt(ui[i]);
    cout << "__popcnt(0x" << hex << ui[i] << ") = " << dec << uir << endl;
  }
}
```

```Output
__popcnt16(0x0) = 0
__popcnt16(0xff) = 8
__popcnt16(0xffff) = 16
__popcnt(0x0) = 0
__popcnt(0xff) = 8
__popcnt(0xffff) = 16
__popcnt(0xffffffff) = 32
```

**Microsoft 전용 종료**

고급 마이크로 장치, inc 저작권 2007 All rights reserved. 고급 마이크로 장치, Inc. 사용 권한을 사용 하 여 재현

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)
